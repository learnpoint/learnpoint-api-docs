Endpoint: bulkapi/v2/[tenant]/students
============================

Return data: [StudentsApiResponse](/models.md#studentsapiresponse)

Supported parameters
--------------------

**datascoperootgroupid** (int optional) *Limits the scope of returned data to the specified group and its child groups.*
**studentsfilter.hasactiveeducation** (bool optional) Default true. *Limits the scope of returned data to students with active education.*

Example URLs
------------

* https://api.learnpoint.se/bulkapi/v2/yhskolan/students
* https://api.learnpoint.se/bulkapi/v2/yhskolan/students?datascoperootgroupid=27&studentsfilter.hasactiveeducation=false

Sample data
-----------

For sake of brevity these are only partial results intended to give an overview of the data structures. Please explore real data sets for a more in-depth understanding.

```json
{
    "ApiVersion": "2.7.20210517102646",
    "Data": {
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
                "HomePhone": null,
                "EducationPlans": [
                    {
                        "Id": 1,
                        "Parts": [
                            {
                                "Code": "EK15",
                                "Name": "Ekonomiassistent 2015",
                                "Type": {
                                    "Code": "Program"
                                }
                            }
                        ],
                        "State": {
                            "Name": "Inskriven",
                            "IsActiveStudent": true,
                            "FromDate": "2016-02-04T00:00:00"
                        }
                    },
                    {
                        "Id": 104,
                        "Parts": [
                            {
                                "Code": "TEK15",
                                "Name": "Teknikkonsult 2015",
                                "Type": {
                                    "Code": "Program"
                                }
                            }
                        ],
                        "State": {
                            "Name": "Studieavbrott",
                            "IsActiveStudent": false,
                            "FromDate": "2016-08-12T11:10:00"
                        }
                    }
                ],
                "Groups": [
                    {
                        "Group": {
                            "Id": 1
                        },
                        "GroupRoles": [
                            {
                                "Id": 16
                            },
                            {
                                "Id": 7
                            }
                        ]
                    },
                    {
                        "Group": {
                            "Id": 4
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
                        "Group": {
                            "Id": 24
                        },
                        "GroupRoles": [
                            {
                                "Id": 20
                            },
                            {
                                "Id": 8
                            }
                        ]
                    },
                    {
                        "Group": {
                            "Id": 28
                        },
                        "GroupRoles": [
                            {
                                "Id": 20
                            },
                            {
                                "Id": 8
                            }
                        ]
                    },
                    {
                        "Group": {
                            "Id": 30
                        },
                        "GroupRoles": [
                            {
                                "Id": 20
                            },
                            {
                                "Id": 8
                            }
                        ]
                    },
                    {
                        "Group": {
                            "Id": 32
                        },
                        "GroupRoles": [
                            {
                                "Id": 20
                            },
                            {
                                "Id": 8
                            }
                        ]
                    },
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
                    "ExtendedProperties": [
                        {
                            "Name": "OFFICIAL_EDUCATION_CODE_MYH",
                            "Value": "YH00123-4"
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
                    "Id": 16,
                    "Name": "Studerande"
                },
                {
                    "Id": 7,
                    "Name": "Medlem"
                },
                {
                    "Id": 2,
                    "Name": "Medlem"
                },
                {
                    "Id": 14,
                    "Name": "Studerande"
                },
                {
                    "Id": 20,
                    "Name": "Studerande"
                },
                {
                    "Id": 8,
                    "Name": "Medlem"
                }
            ]
        }
    }
}
```
