# basic-network

## SRC
* https://github.com/ned1313/advanced-networking-on-aws

## basic-network.template
````json
{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "Basic VPC deployment with two public subnets in two different Availability Zones",
    "Parameters": {},
    "Resources": {
        "VPC": {
            "Type": "AWS::EC2::VPC",
            "Properties": {
                "EnableDnsSupport": "true",
                "EnableDnsHostnames": "true",
                "CidrBlock": "10.0.0.0/16",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Name",
                        "Value": "globo-primary"
                    }
                ]
            }
        },
        "PublicSubnet1": {
            "Type": "AWS::EC2::Subnet",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "CidrBlock": "10.0.1.0/24",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Network",
                        "Value": "Public"
                    },
                    {
                        "Key": "Name",
                        "Value": "subnet-1"
                    }
                ],
                "AvailabilityZone": {
                    "Fn::Select": [
                        "0",
                        {
                            "Fn::GetAZs": ""
                        }
                    ]
                }
            }
        },
        "PublicSubnet2": {
            "Type": "AWS::EC2::Subnet",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "CidrBlock": "10.0.2.0/24",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Network",
                        "Value": "Public"
                    },
                    {
                        "Key": "Name",
                        "Value": "subnet-2"
                    }
                ],
                "AvailabilityZone": {
                    "Fn::Select": [
                        "1",
                        {
                            "Fn::GetAZs": ""
                        }
                    ]
                }
            }
        },
        "PublicSubnet3": {
            "Type": "AWS::EC2::Subnet",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "CidrBlock": "10.0.3.0/24",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Network",
                        "Value": "Private"
                    },
                    {
                        "Key": "Name",
                        "Value": "subnet-3"
                    }
                ],
                "AvailabilityZone": {
                    "Fn::Select": [
                        "2",
                        {
                            "Fn::GetAZs": ""
                        }
                    ]
                }
            }
        },
        "PrivateSubnet1": {
            "Type": "AWS::EC2::Subnet",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "CidrBlock": "10.0.4.0/24",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Network",
                        "Value": "Private"
                    },
                    {
                        "Key": "Name",
                        "Value": "subnet-4"
                    }
                ],
                "AvailabilityZone": {
                    "Fn::Select": [
                        "0",
                        {
                            "Fn::GetAZs": ""
                        }
                    ]
                }
            }
        },
        "PrivateSubnet2": {
            "Type": "AWS::EC2::Subnet",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "CidrBlock": "10.0.5.0/24",
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    },
                    {
                        "Key": "Network",
                        "Value": "Private"
                    },
                    {
                        "Key": "Name",
                        "Value": "subnet-5"
                    }
                ],
                "AvailabilityZone": {
                    "Fn::Select": [
                        "1",
                        {
                            "Fn::GetAZs": ""
                        }
                    ]
                }
            }
        },
        "InternetGateway": {
            "Type": "AWS::EC2::InternetGateway",
            "Properties": {
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    }
                ]
            }
        },
        "GatewayToInternet": {
            "Type": "AWS::EC2::VPCGatewayAttachment",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "InternetGatewayId": {
                    "Ref": "InternetGateway"
                }
            }
        },
        "PublicRouteTable": {
            "Type": "AWS::EC2::RouteTable",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    }
                ]
            }
        },
        "PublicRoute": {
            "Type": "AWS::EC2::Route",
            "DependsOn": "GatewayToInternet",
            "Properties": {
                "RouteTableId": {
                    "Ref": "PublicRouteTable"
                },
                "DestinationCidrBlock": "0.0.0.0/0",
                "GatewayId": {
                    "Ref": "InternetGateway"
                }
            }
        },
        "PublicSubnetRouteTableAssociation1": {
            "Type": "AWS::EC2::SubnetRouteTableAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet1"
                },
                "RouteTableId": {
                    "Ref": "PublicRouteTable"
                }
            }
        },
        "PublicSubnetRouteTableAssociation2": {
            "Type": "AWS::EC2::SubnetRouteTableAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet2"
                },
                "RouteTableId": {
                    "Ref": "PublicRouteTable"
                }
            }
        },
        "PublicSubnetRouteTableAssociation3": {
            "Type": "AWS::EC2::SubnetRouteTableAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet3"
                },
                "RouteTableId": {
                    "Ref": "PublicRouteTable"
                }
            }
        },
        "PublicNetworkAcl": {
            "Type": "AWS::EC2::NetworkAcl",
            "Properties": {
                "VpcId": {
                    "Ref": "VPC"
                },
                "Tags": [
                    {
                        "Key": "Company",
                        "Value": "Globomantics"
                    }
                ]
            }
        },
        "OutboundPublicNetworkAclEntry": {
            "Type": "AWS::EC2::NetworkAclEntry",
            "Properties": {
                "NetworkAclId": {
                    "Ref": "PublicNetworkAcl"
                },
                "RuleNumber": "100",
                "Protocol": "-1",
                "RuleAction": "allow",
                "Egress": "true",
                "CidrBlock": "0.0.0.0/0"
            }
        },
        "InboundPublicNetworkAclEntry": {
            "Type": "AWS::EC2::NetworkAclEntry",
            "Properties": {
                "NetworkAclId": {
                    "Ref": "PublicNetworkAcl"
                },
                "RuleNumber": "100",
                "Protocol": "-1",
                "RuleAction": "allow",
                "Egress": "false",
                "CidrBlock": "0.0.0.0/0"
            }
        },
        "PublicSubnetNetworkAclAssociation1": {
            "Type": "AWS::EC2::SubnetNetworkAclAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet1"
                },
                "NetworkAclId": {
                    "Ref": "PublicNetworkAcl"
                }
            }
        },
        "PublicSubnetNetworkAclAssociation2": {
            "Type": "AWS::EC2::SubnetNetworkAclAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet2"
                },
                "NetworkAclId": {
                    "Ref": "PublicNetworkAcl"
                }
            }
        },
        "PublicSubnetNetworkAclAssociation3": {
            "Type": "AWS::EC2::SubnetNetworkAclAssociation",
            "Properties": {
                "SubnetId": {
                    "Ref": "PublicSubnet3"
                },
                "NetworkAclId": {
                    "Ref": "PublicNetworkAcl"
                }
            }
        }
    },
    "Outputs": {
        "VPCId": {
            "Description": "VPCId of the newly created VPC",
            "Value": {
                "Ref": "VPC"
            }
        }
    }
}
````

---

## 
