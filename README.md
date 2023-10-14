# Creating an AWS VPC 🚀

Follow these steps to set up your AWS Virtual Private Cloud (VPC):

 🏗️ Create a VPC -> `vpc-aws-ec2` \
 🌐 Set IPv4 CIDR to `10.0.0.0/16` \
 🏢 Create a Subnet for public -> `vpc-aws-public-subnet` \
 🆔 Set VPC ID to the selected `vps-aws-ec2` \
 🌏 Choose Availability Zone -> `Asia Pacific/ap-south-1a` \
 🌐 Set IPv4 subnet CIDR block to `10.0.0.0/24` \
 🏢 Create a Subnet for private -> `vpc-aws-private-subnet` \
 🆔 Set VPC ID to the selected `vps-aws-ec2` \
 🌏 Choose Availability Zone -> `Asia Pacific/ap-south-1a` \
 🌐 Set IPv4 subnet CIDR block to `10.0.1.0/24` \
 🌐 Create an internet gateway -> `vpc-aws-igtw` \
 🔄 Attach it to the VPC -> `vpc-aws-ec2` \
 🛣️ Create a Route table -> `vpc-aws-public-route` \
 🆚 Select the VPC -> `vpc-aws-ec2` \
 🛣️ Create a Route table -> `vpc-aws-private-route` \
 🆚 Select the VPC -> `vpc-aws-ec2` \
 🖱️ Click on `vpc-aws-public-route` -> Select subnet associations -> Edit subnet association -> Add `vpc-aws-public-subnet` \
 🔁 Repeat above step for `vps-aws-private-route` \
 🖱️ Click on `vpc-aws-public-route` -> Select route -> Edit route -> Add internet gateway -> `vpc-aws-igtw` \
 🌐 Select NAT gateways -> Create NAT gateway -> `vpc-aws-NAT` -> Select `vpc-aws-public-subnet` -> Select public -> Allocate Elastic IP. \
 🛣️ Select Route table -> `vpc-aws-private-route` -> Edit route -> Select NAT -> `vpc-aws-NAT` \
 🏢 Create an EC2 instance -> `vpc-aws-public-ec2` -> Select `vpc-aws-ec2` -> Select subnet `vpc-aws-public-subnet` -> Enable Auto-assign public IP \
 🏢 Create an EC2 instance -> `vpc-aws-private-ec2` -> Select `vpc-aws-ec2` -> Select subnet `vpc-aws-private-subnet` -> Disable Auto-assign public IP \
 🚀 Try to perform SSH into `vps-aws-private-ec2` from `vps-aws-public-ec2` -> ping `0.0.0.0`. \
 \
If you get the ping, your VPC is working perfectly! 🎉
