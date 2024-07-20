# An AWS VPC using Terraform

Create a VPC on AWS using Terraform

## Overview
This setup creates a foundational VPC infrastructure with public and private subnets, suitable for hosting private instances and public instances.

## Components

### VPC Creation
A VPC with the CIDR block `10.0.0.0/16` will be created.

### Elastic IP and NAT Gateway
An Elastic IP will be allocated and a NAT gateway will be created for the private subnets.

### Internet Gateway
An Internet Gateway will be created for the public subnets.

### Subnets
- **Public Subnets**:
  - `10.0.1.0/24`
  - `10.0.2.0/24`
  - `10.0.3.0/24`
- **Private Subnets**:
  - `10.0.10.0/24`
  - `10.0.11.0/24`
  - `10.0.12.0/24`

### Route Tables
- **Public Route Table**:
  - Associated with the Internet Gateway.
- **Private Route Table**:
  - Associated with the NAT Gateway.

### Route Table Associations
Public and private subnets are associated with their respective route tables.



## Cost estimate

```
Project: gordonmurray/terraform_aws_vpc/.

 Name                     Monthly Qty  Unit              Monthly Cost

 aws_nat_gateway.main
 ├─ NAT gateway                   730  hours                   $32.85
 └─ Data processed     Monthly cost depends on usage: $0.045 per GB

 OVERALL TOTAL                                                $32.85

*Usage costs can be estimated by updating Infracost Cloud settings, see docs for other options.

──────────────────────────────────
20 cloud resources were detected:
∙ 1 was estimated
∙ 19 were free

┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃ Project                                            ┃ Baseline cost ┃ Usage cost* ┃ Total cost ┃
┣━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╋━━━━━━━━━━━━━━━╋━━━━━━━━━━━━━╋━━━━━━━━━━━━┫
┃ main                                               ┃           $33 ┃           - ┃        $33 ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┻━━━━━━━━━━━━━━━┻━━━━━━━━━━━━━┻━━━━━━━━━━━━┛
```

