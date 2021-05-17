Endpoint: bulkapi/v2/[tenant]/groups
==========================

Return data: [GroupsApiResponse](/models.md#groupsapiresponse)

Supported parameters
--------------------

**datascoperootgroupid** (int optional) *Limits the scope of returned data to the specified group and its child groups.*
**includecurrentandfuturegroupsonly** (bool optional) Default true. *Limits the scope of returned data to current and future groups.*

Example URLs
------------
* https://api.learnpoint.se/bulkapi/v2/yhskolan/groups 
* https://api.learnpoint.se/bulkapi/v2/yhskolan/groups?datascoperootgroupid=863&includecurrentandfuturegroupsonly=false 

Sample data
-----------

For sake of brevity these are only partial results intended to give an overview of the data structures. Please explore real data sets for a more in-depth understanding.

```json
{
    "ApiVersion": "2.6.20210517102646",
    "Data": {
        "Groups": [
            {
                "Id": 1,
                "Name": "Yh-skolan",
                "Code": "Yh-skolan",
                "LifespanFrom": null,
                "LifespanUntil": null,
                "Category": {
                    "Code": "School",
                    "Name": "Skola"
                },
                "StaffGroupMembers": [
                    {
                        "StaffMember": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 7
                            },
                            {
                                "Id": 27
                            }
                        ]
                    },
                    {
                        "StaffMember": {
                            "Id": 2
                        },
                        "GroupRoles": [
                            {
                                "Id": 7
                            },
                            {
                                "Id": 27
                            }
                        ]
                    }
                ],
                "StudentGroupMembers": [
                    {
                        "Student": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 7
                            },
                            {
                                "Id": 16
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 2
                        },
                        "GroupRoles": [
                            {
                                "Id": 7
                            },
                            {
                                "Id": 16
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 3
                        },
                        "GroupRoles": [
                            {
                                "Id": 7
                            },
                            {
                                "Id": 16
                            }
                        ]
                    }
                ]
            },
            {
                "Id": 24,
                "Name": "Att arbeta i näringslivet",
                "Code": "EK15_AAN",
                "LifespanFrom": "2016-01-31T23:00:00Z",
                "LifespanUntil": "2016-02-29T22:59:00Z",
                "Category": {
                    "Code": "CourseInstance",
                    "Name": "Kurs"
                },
                "ParentGroup": {
                    "Group": {
                        "Id": 4
                    },
                    "ParentGroup": {
                        "Group": {
                            "Id": 1
                        }
                    }
                },
                "CourseDefinition": {
                    "Id": 1
                },
                "StaffGroupMembers": [
                    {
                        "StaffMember": {
                            "Id": 1
                        },
                        "IsGroupManager": true,
                        "GroupRoles": [
                            {
                                "Id": 8
                            },
                            {
                                "Id": 10
                            },
                            {
                                "Id": 21
                            },
                            {
                                "Id": 33
                            }
                        ]
                    },
                    {
                        "StaffMember": {
                            "Id": 3
                        },
                        "IsGroupManager": false,
                        "GroupRoles": [
                            {
                                "Id": 8
                            },
                            {
                                "Id": 10
                            },
                            {
                                "Id": 21
                            }
                        ]
                    }
                ],
                "StudentGroupMembers": [
                    {
                        "Student": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 8
                            },
                            {
                                "Id": 20
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 2
                        },
                        "GroupRoles": [
                            {
                                "Id": 8
                            },
                            {
                                "Id": 20
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 3
                        },
                        "GroupRoles": [
                            {
                                "Id": 8
                            },
                            {
                                "Id": 20
                            }
                        ]
                    }
                ]
            }
        ],
        "ParentGroups": [
            {
                "Id": 4,
                "Name": "Ekonomiassistent 2015",
                "Code": "EK15",
                "LifespanFrom": "2015-08-17T10:42:23Z",
                "LifespanUntil": "2017-06-09T10:42:23Z",
                "Category": {
                    "Code": "EducationInstance",
                    "Name": "Klass"
                },
                "ParentGroup": {
                    "Group": {
                        "Id": 1
                    }
                },
                "StaffGroupMembers": [
                    {
                        "StaffMember": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 2
                            },
                            {
                                "Id": 25
                            },
                            {
                                "Id": 26
                            }
                        ],
                        "IsGroupManager": true
                    },
                    {
                        "StaffMember": {
                            "Id": 2
                        },
                        "GroupRoles": [
                            {
                                "Id": 2
                            },
                            {
                                "Id": 25
                            }
                        ],
                        "IsGroupManager": false
                    }
                ],
                "StudentGroupMembers": [
                    {
                        "Student": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 2
                            },
                            {
                                "Id": 14
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 2
                        },
                        "GroupRoles": [
                            {
                                "Id": 2
                            },
                            {
                                "Id": 14
                            }
                        ]
                    },
                    {
                        "Student": {
                            "Id": 3
                        },
                        "GroupRoles": [
                            {
                                "Id": 2
                            },
                            {
                                "Id": 14
                            }
                        ]
                    }
                ]
            }
        ],
        "ReferenceData": {
            "StaffMembers": [
                {
                    "Id": 1,
                    "NationalRegistrationNumber": "19XXXXXX-XX21",
                    "Signature": "PSN",
                    "FirstName": "Pelle",
                    "LastName": "Persson",
                    "Username": "yhskolan.p.persson",
                    "Email": "daniel.gidlof@viaecole.se",
                    "Email2": null,
                    "MobilePhone": "073-XXXXXX",
                    "MayExposeMobilePhoneToStudents": true
                },
                {
                    "Id": 2,
                    "NationalRegistrationNumber": null,
                    "Signature": "HHA",
                    "FirstName": "Hasse",
                    "LastName": "Hansson",
                    "Username": "yhskolan.h.hansson",
                    "Email": "martin.vehmas@viaecole.se",
                    "Email2": null,
                    "MobilePhone": null,
                    "MayExposeMobilePhoneToStudents": true
                },
                {
                    "Id": 3,
                    "NationalRegistrationNumber": null,
                    "Signature": "AAN",
                    "FirstName": "Anders",
                    "LastName": "Andersson",
                    "Username": "yhskolan.a.andersson",
                    "Email": "anders.andersson@yh-skolan.se",
                    "Email2": null,
                    "MobilePhone": null,
                    "MayExposeMobilePhoneToStudents": false
                }
            ],
            "Students": [
                {
                    "Id": 1,
                    "NationalRegistrationNumber": "19790201-0101",
                    "FirstName": "Maria",
                    "LastName": "Axelsson",
                    "Username": "yhskolan.m.axelsson",
                    "Email": "testapplicant37@test.yh-antagning.se",
                    "Email2": null,
                    "MobilePhone": "073-3212555",
                    "HomeAddress": {
                        "CO": null,
                        "Street": "Gatan 7",
                        "City": "Stockholm",
                        "Zip": "123 45"
                    },
                    "HomePhone": null
                },
                {
                    "Id": 2,
                    "NationalRegistrationNumber": "19890102-3002",
                    "FirstName": "Karin",
                    "LastName": "Berg",
                    "Username": "yhskolan.karin.berg",
                    "Email": "testapplicant50@test.yh-antagning.se",
                    "Email2": null,
                    "MobilePhone": "073212555",
                    "HomeAddress": {
                        "CO": null,
                        "Street": "Vägen 23",
                        "City": "Stockholm",
                        "Zip": "12247"
                    },
                    "HomePhone": null
                },
                {
                    "Id": 3,
                    "NationalRegistrationNumber": "19850203-0103",
                    "FirstName": "Stig",
                    "LastName": "Berg",
                    "Username": "yhskolan.stig.berg",
                    "Email": "testapplicant1@test.yh-antagning.se",
                    "Email2": null,
                    "MobilePhone": "073-555153",
                    "HomeAddress": {
                        "CO": null,
                        "Street": "Gatan 73",
                        "City": "Utbildningsbyn",
                        "Zip": "433 67"
                    },
                    "HomePhone": null
                }
            ],
            "GroupRoles": [
                {
                    "Id": 2,
                    "Name": "Medlem"
                },
                {
                    "Id": 7,
                    "Name": "Medlem"
                },
                {
                    "Id": 8,
                    "Name": "Medlem"
                },
                {
                    "Id": 10,
                    "Name": "Lärarmedlem"
                },
                {
                    "Id": 14,
                    "Name": "Studerande"
                },
                {
                    "Id": 16,
                    "Name": "Studerande"
                },
                {
                    "Id": 20,
                    "Name": "Studerande"
                },
                {
                    "Id": 21,
                    "Name": "Ansvarig lärare"
                },
                {
                    "Id": 25,
                    "Name": "Personal"
                },
                {
                    "Id": 26,
                    "Name": "Utbildningsledare"
                },
                {
                    "Id": 27,
                    "Name": "Personal"
                },
                {
                    "Id": 33,
                    "Name": "Utbildningsledare"
                }
            ],
            "CourseDefinitions": [
                {
                    "Id": 1,
                    "Code": "EK15_AAN",
                    "Name": "Att arbeta i näringslivet",
                    "IsInternship": false
                }
            ]
        }
    }
}
```
