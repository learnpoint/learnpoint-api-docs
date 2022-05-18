Endpoint: bulkapi/v2/[tenant]/staffmembers
================================

Return data: [StaffMembersApiResponse](/models.md#StaffMembersApiResponse)

Supported parameters
--------------------

**datascoperootgroupid** (int optional) *Limits the scope of returned data to the specified group and its child groups.*

Example URLs
------------

* https://api.learnpoint.se/bulkapi/v2/yhskolan/staffmembers
* https://api.learnpoint.se/bulkapi/v2/yhskolan/staffmembers?datascoperootgroupid=168

Sample data
-----------

For sake of brevity these are only partial results intended to give an overview of the data structures. Please explore real data sets for a more in-depth understanding.

```json
{
    "ApiVersion": "2.7.20210517102646",
    "Data": {
        "StaffMembers": [
            {
                "Id": 1,
                "NationalRegistrationNumber": "19XXXXXX-XX21",
                "Signature": "PSN",
                "FirstName": "Pelle",
                "LastName": "Persson",
                "Username": "yhskolan.p.persson",
                "Email": "pelle.persson@yhskolan.se",
                "Email2": null,
                "MobilePhone": "073-XXXXXX",
                "MayExposeMobilePhoneToStudents": true,
                "WorkPhone": "074-XXXXXX",
                "MayExposeWorkPhoneToStudents": true,
                "StaffFunctions": [
                    {
                        "Id": 1,
                        "Name": "Administratör"
                    }
                ],
                "Groups": [
                    {
                        "Group": {
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
                        "Group": {
                            "Id": 4
                        },
                        "IsGroupManager": true,
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
                        ]
                    },
                    {
                        "Group": {
                            "Id": 24
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
                        "Group": {
                            "Id": 28
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
                        "Group": {
                            "Id": 30
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
                        "Group": {
                            "Id": 32
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
                    }
                ]
            }
        ],
        "ReferenceData": {
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
                    }
                },
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
                    "CustomProperties": [
                        {
                            "Name": "MYH Utbildningsnummer",
                            "Value": "YH12345-2021-1"
                        }
                    ]
                },
                {
                    "Id": 24,
                    "Name": "Företagsekonomi",
                    "Code": "EK15_FEK",
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
                    }
                },
                {
                    "Id": 28,
                    "Name": "Grundkurs ekonomi",
                    "Code": "EK15_GEK",
                    "LifespanFrom": "2015-11-08T23:00:00Z",
                    "LifespanUntil": "2015-12-18T22:59:00Z",
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
                    }
                },
                {
                    "Id": 30,
                    "Name": "Teknikkurs 1",
                    "Code": "EK15_TEK1",
                    "LifespanFrom": "2015-12-13T23:00:00Z",
                    "LifespanUntil": "2016-02-12T22:59:00Z",
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
                    }
                },
                {
                    "Id": 32,
                    "Name": "Teknikkurs 2",
                    "Code": "EK15_TEK2",
                    "LifespanFrom": "2016-01-31T23:00:00Z",
                    "LifespanUntil": "2016-04-08T21:59:00Z",
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
                    }
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
            ]
        }
    }
}
```
