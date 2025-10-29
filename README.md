LearnPoint Bulk API v2.8
======================

LearnPoint Bulk API is an HTTP based, REST-like API. Its primary purpose is to make LearnPoint data accessible to other applications. These applications can use the data to populate other systems for e.g. scheduling, resource planning or intranet access.

## DEPRECATED

Learnpoint Bulk API version 2 is deprecated.

### Migrate to Learnpoint API version 3

Information about changes: [Migration from Learnpoint Bulk API to Learnpoint API v3](v2-v3.md)

Documentation for Learnpoint API v3: [https://api.learnpoint.se/docs](https://api.learnpoint.se/docs)

AUTHENTICATION
--------------

API authentication is based on OAuth2 access tokens. Tokens are obtained by calling a token endpoint on https://login.learnpoint.se. The protocol of the token endpoint is based on OAuth2/Open ID Connect. The client credentials used for authentication at the token endpoint are provided by ViaEcole. 

BASIC FLOW
----------

* The client submits its client credentials to https://login.learnpoint.se.         
* The client receives an OAuth2 access token which will grant the client access to the API.
* The client calls the desired API endpoint, passing the access token in an http authorization header.
* The client receives JSON data.

API ENDPOINTS
-------------

* [bulkapi/v2/[tenant]/students](endpoints/students.md) 
* [bulkapi/v2/[tenant]/groups](endpoints/groups.md) 
* [bulkapi/v2/[tenant]/staffmembers](endpoints/staffmembers.md) 

API MODELS
----------

The endpoints returns corresponding JSON data defined by the models [StudentsApiResponse](models.md#StudentsApiResponse), [GroupsApiResponse](models.md#GroupsApiResponse) and [StaffMembersApiResponse](models.md#StaffMembersApiResponse).

Where JSON data may be omitted it is noted in the model descriptions. Possible null values are marked by a question mark, e.g. string?.

### Student models

* [StudentsApiResponse](models.md#StudentsApiResponse)
* [StudentsData](models.md#StudentsData)
* [StudentsReferenceData](models.md#StudentsReferenceData)
* [Student](models.md#Student)
* [StudentHomeAddress](models.md#StudentHomeAddress)
* [FullStudent](models.md#FullStudent)
* [StudentGroup](models.md#StudentGroup)
* [StudentEducationPlan](models.md#StudentEducationPlan)
* [StudentEducationPlanState](models.md#StudentEducationPlanState)
* [EducationPlan](models.md#EducationPlan)
* [EducationPlanType](models.md#EducationPlanType)
* [StudentReference](models.md#StudentReference)

### Group models

* [GroupsApiResponse](models.md#GroupsApiResponse)
* [GroupsData](models.md#GroupsData)
* [GroupsReferenceData](models.md#GroupsReferenceData)
* [Group](models.md#Group)
* [GroupCategory](models.md#GroupCategory)
* [ParentGroupReference](models.md#ParentGroupReference)
* [ExtendedProperty](models.md#ExtendedProperty)
* [FullGroup](models.md#FullGroup)
* [GroupStaffMember](models.md#GroupStaffMember)
* [GroupStudent](models.md#GroupStudent)
* [GroupReference](models.md#GroupReference)
* [GroupRole](models.md#GroupRole)
* [GroupRoleReference](models.md#GroupRoleReference)

### Staff member models

* [StaffMembersApiResponse](models.md#StaffMembersApiResponse)
* [StaffMembersData](models.md#StaffMembersData)
* [StaffMembersReferenceData](models.md#StaffMembersReferenceData)
* [StaffMember](models.md#StaffMember)
* [FullStaffMember](models.md#FullStaffMember)
* [StaffMemberGroup](models.md#StaffMemberGroup)
* [StaffMemberReference](models.md#StaffMemberReference)

### Course definition models

* [CourseDefinition](models.md#CourseDefinition)
* [CourseDefinitionReference](models.md#CourseDefinitionReference)

### General models
* [ApiError](models.md#ApiError)

SCOPES
----------
* learnpointbulkapi.read
  * Access to Learnpoint Bulk API
* learnpointbulkapi.mobilephone.read
  * Access to mobile phone numbers for students and staff
* learnpointbulkapi.phone2.read
  * Access to Phone2 number for staff
* learnpointbulkapi.homeaddress.read
  * Access to home address for students

SAMPLE CODE
-----------

This .NET Core C# code sample fetches a access token and calls the three endpoints.

```C#
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Text;
using System.Text.Json;


namespace SimpleSample
{
    class Program
    {
        static void Main(string[] args)
        {
            string clientId = "yhskolan.apiclient";
            string clientSecret = "xxxxxxxxxxxxxxxxxx";
            string requestedScopes = "learnpointbulkapi.read learnpointbulkapi.mobilephone.read learnpointbulkapi.phone2.read learnpointbulkapi.homeaddress.read";
            string tenantIdentifier = "yhskolan";

            //Get Access token
            var tokenHttpClient = new HttpClient();
            var credentials = $"{clientId}:{clientSecret}";
            var base64Credentials = Convert.ToBase64String(Encoding.UTF8.GetBytes(credentials));
            tokenHttpClient.DefaultRequestHeaders.Authorization = new System.Net.Http.Headers.AuthenticationHeaderValue("Basic", base64Credentials);
            var tokenResponse = tokenHttpClient.PostAsync("https://login.learnpoint.se/connect/token",
                                                            new FormUrlEncodedContent(new Dictionary<string, string>{
                                                                { "grant_type", "client_credentials" },
                                                                { "scope", requestedScopes }
                                                                })).Result;
            var tokenResponseContent = tokenResponse.Content.ReadAsStringAsync().Result;
            //Construct a JSON document from the response and extract the AccessToken
            var tokenResponseJSON = JsonDocument.Parse(tokenResponseContent);
            string accessToken = null;
            if (tokenResponseJSON.RootElement.TryGetProperty("access_token", out JsonElement accessTokenJSONValue))
            {
                accessToken = accessTokenJSONValue.ToString();
            }

            //Fetch from API
            var client = new HttpClient
            {
                BaseAddress = new Uri("https://api.learnpoint.se")
            };
            client.DefaultRequestHeaders.Authorization = new System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", accessToken);

            string jsonStudents = client.GetStringAsync($"/bulkapi/v2/{tenantIdentifier}/students").Result;
            Console.WriteLine(jsonStudents);

            string jsonGroups = client.GetStringAsync($"/bulkapi/v2/{tenantIdentifier}/groups").Result;
            Console.WriteLine(jsonGroups);

            string jsonStaffMembers = client.GetStringAsync($"/bulkapi/v2/{tenantIdentifier}/staffmembers").Result;
            Console.WriteLine(jsonStaffMembers);
        }
    }
}
```

VERSION HISTORY
---------------

### ApiVersion 2.8

* Added UserId to models Student, FullStudent, StaffMember and FullStaffMember.
  * Preparation for migration to Learnpoint API v3.
* Added ProgramEnrollmentId to StudentEducationPlan
  * Preparation for migration to Learnpoint API v3. 

### ApiVersion 2.7

* Added Phone2 (string?) to models StaffMember and FullStaffMember.
  * New scope for Phone2: learnpointbulkapi.phone2.read
* Added StaffFunctions to FullStaffMember
* Added ExtendedProperties to Group and FullGroup
* Added Points to CourseDefinition

### ApiVersion 2.6

* Added Email2 (string?) to models Student, FullStudent, StaffMember and FullStaffMember.

### ApiVersion 2.5

* Added Id (int) to model StudentEducationPlan.
* Added parameter includecurrentandfuturegroupsonly (bool optional) to endpoint Groups.
* Added parameter studentsfilter.hasactiveeducation (bool optional) to endpoint Students.

### ApiVersion 2.4

* Added FromDate (date?) to model StudentEducationPlanState.

### ApiVersion 2.3

* Added parameter datascoperootgroupid (int optional) to endpoint Students, Groups and StaffMembers.

### ApiVersion 2.2

* Adding GroupRoles and StudentEducationPlans.

### ApiVersion 2.1

* Adding version info to JSON result.
