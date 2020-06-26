## Providers

| Name | Version |
|------|---------|
| aws | >= 2.68.0 |
| template | >= 2.1 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| aws\_account\_id | The root user of the AWS account provided will be the sole credentials KMS key administrator. | `string` | n/a | yes |
| aws\_automation\_role\_arn | The automation role used by Terraform. Gets decrypt/encrypt access to KMS credentials key. | `string` | n/a | yes |
| foundry\_password | Will be encrypted in AWS Parameter Store for exclusive use by the Foundry server to configure the tool. | `string` | n/a | yes |
| foundry\_username | Will be encrypted in AWS Parameter Store for exclusive use by the Foundry server to configure the tool. | `string` | n/a | yes |
| home\_ip\_address | The public IP address of your home network; the only IP allowed to SSH to the Foundry server instance. | `string` | n/a | yes |
| region | The closest region to you and/or your party, to minimize latency. | `string` | n/a | yes |
| artifacts\_data\_expiration\_days | The amount of days after which non-current version of Foundry data is expired. | `number` | `30` | no |
| ebs\_block\_devices | Should you want to mount any ebs block devices, such as for data storage, do so here. | <pre>list(object({<br>    device_name = string<br>  }))</pre> | `[]` | no |
| foundry\_admin\_key | The Admin Access Key to set for password-protecting administration access to the Foundry tool. Will be encrypted in AWS Parameter Store for exclusive use by the server. | `string` | `""` | no |
| foundry\_artifacts\_bucket\_public | Whether or not the artifacts bucket should be public. To reuse this bucket for direct Amazon S3 asset storage in browser, set to true. | `bool` | `false` | no |
| foundryvtt\_docker\_image | Probably won't work with other images yet but the option is there if you want to experiment | `string` | `"felddy/foundryvtt:latest"` | no |
| instance\_type | The instance type on which the Foundry server runs. Defaults to free tier eligible type. | `string` | `"t2.micro"` | no |
| key\_name | The name of the key to use for SSH. Can be easily be generated as a key-pair in the AWS console. | `string` | `""` | no |
| security\_groups | Any extra security groups to associate with the Foundry server. | `list` | `[]` | no |
| tags | n/a | <pre>list(object({<br>    key   = string,<br>    value = string<br>  }))</pre> | `[]` | no |
| vpc\_cidr\_block | The CIDR block for the VPC. | `string` | `"20.0.0.0/16"` | no |

## Outputs

| Name | Description |
|------|-------------|
| artifacts\_bucket\_arn | n/a |
| artifacts\_bucket\_name | n/a |
| asg\_arn | n/a |
| asg\_azs | n/a |
| asg\_id | n/a |
| credentials\_kms\_key\_arn | n/a |
| credentials\_kms\_key\_id | n/a |
| instance\_profile\_arn | The ARN of the instance profile the Foundry server uses to access credentials and the artifacts bucket. |
| instance\_profile\_id | The ID of the instance profile the Foundry server uses to access credentials and the artifacts bucket. |
| instance\_profile\_name | The name of the instance profile the Foundry server uses to access credentials and the artifacts bucket. |
| internet\_gateway\_arn | n/a |
| internet\_gateway\_id | n/a |
| launch\_configuration\_arn | n/a |
| launch\_configuration\_id | n/a |
| launch\_configuration\_name | n/a |
| lb\_arn | n/a |
| lb\_dns\_name | n/a |
| lb\_zone\_id | n/a |
| policy\_arn | The ARN of the policy attached to the Foundry server role. |
| policy\_id | The ID of the policy attached to the Foundry server role. |
| policy\_name | The name of the policy attached to the Foundry server role. |
| role\_arn | The ARN of the role the Foundry server uses to access credentials and the artifacts bucket. |
| role\_name | The name of the role the Foundry server uses to access credentials and the artifacts bucket. |
| subnet\_public\_arns | n/a |
| subnet\_public\_azs | n/a |
| subnet\_public\_ids | n/a |
| target\_group\_http\_arn | n/a |
| target\_group\_http\_name | n/a |
| target\_group\_https\_arn | n/a |
| target\_group\_https\_name | n/a |
| vpc\_arn | n/a |
| vpc\_cidr\_block | n/a |
| vpc\_id | n/a |
| vpc\_main\_route\_table\_id | n/a |
