API Models
==========

StudentsApiResponse
-------------------

<pre>
StudentsApiResponse{
   ApiVersion (string),
   Data (<a href="models.md#StudentsData" title="StudentsData">StudentsData</a> optional) <i>Omitted if Error is present</i>, 
   Error (<a href="models.md#ApiError" title="ApiError">ApiError</a> optional) <i>Omitted if Data is present</i>
}
</pre>

StudentsData
------------

<pre>
StudentsData{
   Students (Array[<a href="models.md#FullStudent" title="FullStudent">FullStudent</a>]),
   ReferenceData (<a href="models.md#StudentsReferenceData" title="StudentsReferenceData">StudentsReferenceData</a> optional) <i>Omitted if there are no data references in the document</i>
}
</pre>

StudentsReferenceData
---------------------

<pre>
StudentsReferenceData{
   Groups (Array[<a href="models.md#Group" title="Group">Group</a>] optional) <i>Omitted if there are no GroupReferences in the document</i>
}
</pre>

Student
-------

<pre>
Student{
   Id (int),
   NationalRegistrationNumber (string?),
   FirstName (string),
   LastName (string),
   Username (string?),
   Email (string?),
   Email2 (string?),
   MobilePhone (string? optional) <i>Omitted if the client is not authorized for MobilePhone read access</i>,
   HomeAddress (StudentHomeAddress? optional) <i>Omitted if the client is not authorized for HomeAddress read access</i>,
   HomePhone (string? optional) <i>Omitted if the client is not authorized for HomeAddress read access</i>
}
</pre>

StudentHomeAddress
------------------

<pre>
StudentHomeAddress{
   CO (string?),
   Street (string?),
   City (string?),
   Zip (string?)
}
</pre>

FullStudent
-----------

<pre>
FullStudent{
   Id (int),
   NationalRegistrationNumber (string?),
   FirstName (string),
   LastName (string),
   Username (string?),
   Email (string?),
   Email2 (string?),
   MobilePhone (string?) Omitted if the client is not authorized for MobilePhone read access,
   HomeAddress (StudentHomeAddress?) <i>Omitted if the client is not authorized for HomeAddress read access</i>,
   HomePhone (string?) <i>Omitted if the client is not authorized for HomeAddress read access</i>,
   Groups (Array[<a href="models.md#StudentGroup" title="StudentGroup">StudentGroup</a>]),
   EducationPlans (Array[<a href="models.md#StudentEducationPlan" title="StudentEducationPlan">StudentEducationPlan</a>])
}
</pre>

StudentGroup
------------

<pre>
StudentGroup{
   Group (<a href="models.md#GroupReference" title="GroupReference">GroupReference</a>) <i>This group can be found in StudentsData.ReferenceData</i>
   GroupRoles (Array[<a href="models.md#GroupRoleReference" title="GroupRoleReference">GroupRoleReference</a>]) <i>This grouprole can be found in StudentsData.ReferenceData</i>
}
</pre>

StudentEducationPlan
--------------------

<pre>
StudentEducationPlan{
   Id (int),
   Parts (Array[<a href="models.md#EducationPlan" title="EducationPlan">EducationPlan</a>]),
   State (<a href="models.md#StudentEducationPlanState" title="StudentEducationPlanState">StudentEducationPlanState</a>)
}
</pre>

StudentEducationPlanState
-------------------------

<pre>
StudentEducationPlanState{
   Name (string),
   IsActiveStudent (boolean),
   FromDate (date?)
}
</pre>

EducationPlan
-------------

<pre>
EducationPlan{
   Code (string),
   Name (string), 
   Type (<a href="models.md#EducationPlanType" title="EducationPlanType">EducationPlanType</a>)
}
</pre>

EducationPlanType
-----------------

<pre>
EducationPlanType{
   Code (string)
}
</pre>

StudentReference
----------------

<pre>
StudentReference{
   Id (int)
}
</pre>

GroupsApiResponse
-----------------

<pre>
GroupsApiResponse{
   ApiVersion (string),
   Data (<a href="models.md#groupsdata" title="GroupsData">GroupsData</a> optional) <i>Omitted if Error is present</i>, 
   Error (ApiError optional) <i>Omitted if Data is present</i>
}
</pre>

GroupsData
----------

<pre>
GroupsData{
   Groups (Array[<a href="models.md#fullgroup" title="FullGroup">FullGroup</a>]),
   ParentGroups (Array[<a href="models.md#fullgroup" title="FullGroup">FullGroup</a>] optional) <i>Any parent groups referenced by Groups that do not match the filter criteria to be included in Groups. Omitted if there are no such parent groups</i>,
   ReferenceData (<a href="models.md#groupsreferencedata" title="GroupsReferenceData">GroupsReferenceData</a>, optional) <i>Omitted if there are no data references in the document (except refrences to groups, which are found in either the Groups orParentGroups property)</i>.
}
</pre>

GroupsReferenceData
-------------------

<pre>
GroupsReferenceData{
   StaffMembers (Array[<a href="models.md#staffmember" title="StaffMember">StaffMember</a>] optional) <i>Omitted if there are no StaffMemberReferences in the document</i>
   Students (Array[<a href="models.md#student" title="Student">Student</a>] optional) <i>Omitted if there are no StudentReferences in the document</i>
   CourseDefinitions (Array[<a href="models.md#coursedefinition" title="CourseDefinition">CourseDefinition</a>] optional) <i>Omitted if there are no CourseDefinitionReferences in the document</i>
   GroupRoles (Array[<a href="models.md#grouprole" title="GroupRole">GroupRole</a>] optional) <i>Omitted if there are no GroupRoleReferences in the document</i>
}
</pre>

Group
-----

<pre>
Group{
   Id (int),
   Name (string),
   Code (string),
   LifespanFrom (date?),
   LifespanUntil (date?),
   Category (<a href="models.md#GroupCategory" title="GroupCategory">GroupCategory</a>),
   ParentGroup (<a href="models.md#ParentGroupReference" title="ParentGroupReference">ParentGroupReference</a> optional) <i>Omitted if no parent group</i>,
   ExtendedProperties (<a href="models.md#ExtendedProperty" title="ExtendedProperty">ExtendedProperty</a>) <i>Omitted if no extended properties</i>
}
</pre>

GroupCategory
-------------

<pre>
GroupCategory{
   Name (string),
   Code (string) <i>["School", "EducationInstance", "CourseInstance"]</i>
}
</pre>

ParentGroupReference
--------------------

<pre>
ParentGroupReference{
   Group (<a href="models.md#GroupReference" title="GroupReference">GroupReference</a>) <i>The parent group</i>,
   ParentGroup (<a href="models.md#ParentGroupReference" title="ParentGroupReference">ParentGroupReference</a> optional) <i>Parent group information about the parent group. Omitted if no parent group.</i>
}
</pre>

ExtendedProperty
-------------

<pre>
ExtendedProperty{
   Name (string) <i>["OFFICIAL_EDUCATION_CODE_MYH"]</i>,
   Value (string)
}
</pre>

FullGroup
---------

<pre>
FullGroup{
   Id (int),
   Name (string),
   Code (string),
   LifespanFrom (date?),
   LifespanUntil (date?),
   Category (<a href="models.md#GroupCategory" title="GroupCategory">GroupCategory</a>),
   ParentGroup (<a href="models.md#ParentGroupReference" title="ParentGroupReference">ParentGroupReference</a> optional) <i>Referenced groups can be found in GroupsData.Groups or GroupsData.ParentGroups. Omitted if no parent group, 
   ExtendedProperties (<a href="models.md#ExtendedProperty" title="ExtendedProperty">ExtendedProperty</a>) <i>Omitted if no extended properties</i>,
   CourseDefinition (CourseDefinitionReference optional) Omitted if the group does not reference a CourseDefinition. The course definition can be found in GroupsData.ReferenceData</i>,
   StaffGroupMembers (Array[<a href="models.md#GroupStaffMember" title="GroupStaffMember">GroupStaffMember</a>]),
   StudentGroupMembers (Array[<a href="models.md#GroupStudent" title="GroupStudent">GroupStudent</a>])
}
</pre>

GroupStaffMember
----------------

<pre>
GroupStaffMember{
   StaffMember (<a href="models.md#StaffMemberReference" title="StaffMemberReference">StaffMemberReference</a>) <i>This staff member can be found in GroupsData.ReferenceData</i>,
   IsGroupManager (boolean optional) <i>Omitted if the concept of group manager is not applicable to the group</i>,
   GroupRoles (Array[<a href="models.md#GroupRoleReference" title="GroupRoleReference">GroupRoleReference</a>]) <i>These group roles can be found in GroupsData.ReferenceData</i>
}
</pre>

GroupStudent
------------

<pre>
GroupStudent{
   Student (<a href="models.md#StudentReference" title="StudentReference">StudentReference</a>) <i>This student can be found in GroupsData.ReferenceData</i>
   GroupRoles (Array[<a href="models.md#GroupRoleReference" title="GroupRoleReference">GroupRoleReference</a>]) <i>These group roles can be found in GroupsData.ReferenceData</i>
}
</pre>

GroupReference
--------------

<pre>
GroupReference{
   Id (int)
}
</pre>

GroupRole
---------

<pre>
GroupRole{
   Id (int),
   Name (string)
}
</pre>

GroupRoleReference
------------------

<pre>
GroupRoleReference{
   Id (int)
}
</pre>





StaffMembersApiResponse
-----------------------

<pre>
StaffMembersApiResponse{
   ApiVersion (string),
   Data (<a href="models.md#StaffMembersData" title="StaffMembersData">StaffMembersData</a>, optional) <i>Omitted if Error is present</i>, 
   Error (<a href="models.md#ApiError" title="ApiError">ApiError</a>, optional) <i>Omitted if Data is present</i>
}
</pre>

StaffMembersData
----------------

<pre>
StaffMembersData{
   StaffMembers (Array[<a href="models.md#FullStaffMember" title="FullStaffMember">FullStaffMember</a>]),
   ReferenceData (<a href="models.md#StaffMembersReferenceData" title="StaffMembersReferenceData">StaffMembersReferenceData</a> optional) <i>Omitted if there are no data references in the document.</i>
}
</pre>

StaffMembersReferenceData
-------------------------

<pre>
StaffMembersReferenceData{
   Groups (Array[<a href="models.md#Group" title="Group">Group</a>] optional) <i>Omitted if there are no GroupReferences in the document</i>,
   GroupRoles (Array[<a href="models.md#GroupRole" title="GroupRole">GroupRole</a>] optional) <i>Omitted if there are no GroupRoleReferences in the document</i>
}
</pre>

StaffMember
-----------

<pre>
StaffMember{
   Id (int),
   NationalRegistrationNumber (string?),
   Signature (string?),
   FirstName (string?),
   LastName (string?),
   Username (string?),
   Email (string?),
   Email2 (string?),
   MobilePhone (string? optional) <i>Omitted if the client is not authorized for MobilePhone read access</i>,
   MayExposeMobilePhoneToStudents (boolean optional) <i>Omitted if the client is not authorized for MobilePhone read access</i>
   WorkPhone (string? optional) <i>Omitted if the client is not authorized for WorkPhone read access</i>,
   MayExposeWorkPhoneToStudents (boolean optional) <i>Omitted if the client is not authorized for WorkPhone read access</i>,     
}
</pre>

FullStaffMember
---------------

<pre>
FullStaffMember{
   Id (int),
   NationalRegistrationNumber (string?),
   Signature (string?),
   FirstName (string?),
   LastName (string?),
   Username (string?),
   Email (string?),
   Email2 (string?),
   MobilePhone (string? optional) <i>Omitted if the client is not authorized for MobilePhone read access</i>,
   MayExposeMobilePhoneToStudents (boolean optional) <i>Omitted if the client is not authorized for MobilePhone read access</i>,
   WorkPhone (string? optional) <i>Omitted if the client is not authorized for WorkPhone read access</i>,
   MayExposeWorkPhoneToStudents (boolean optional) <i>Omitted if the client is not authorized for WorkPhone read access</i>,   
   Groups (Array[<a href="models.md#StaffMemberGroup" title="StaffMemberGroup">StaffMemberGroup</a>])
}
</pre>

StaffMemberGroup
----------------

<pre>
StaffMemberGroup{
   Group (<a href="models.md#GroupReference" title="GroupReference">GroupReference</a>) <i>This group can be found in StaffMembersData.ReferenceData</i>,
   IsGroupManager (bool optional) <i>Omitted if the concept of group manager is not applicable to the group</i>,
   GroupRoles (Array[<a href="models.md#GroupRoleReference" title="GroupRoleReference">GroupRoleReference</a>]) <i>This grouprole can be found in StaffMembersData.ReferenceData</i>
}
</pre>

StaffMemberReference
--------------------

<pre>
StaffMemberReference{
   Id (int)
}
</pre>

CourseDefinition
----------------

<pre>
CourseDefinition{
   Id (int),
   Code (string),
   Name (string),
   IsInternship (boolean),
   Points (int),
   Subject (<a href="models.md#Subject" title="Subject">Subject</a> )
}
</pre>

CourseDefinitionReference
-------------------------

<pre>
CourseDefinitionReference{
   Id (int)
}
</pre>

Subject
----------------

<pre>
Subject{
   Id (int),
   Code (string),
   Name (string)
}
</pre>

ApiError
--------

<pre>
ApiError{
   Message (string)
}
</pre>
