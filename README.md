✨ Steps to create an AWS VPC ✨
=================================

🏗️ Create a VPC -> vpc-aws-ec2  \
🌐 IPv4 CIDR -> 10.0.0.0/16  \
🏢 Create a Subnet for public -> vpc-aws-public-subnet \
🆔 VPC ID -> select the vps-aws-ec2 \
🌏 Availability Zone -> Asia Pacific/ap-south-1a \
🌐 IPv4 subnet CIDR block -> 10.0.0.0/24 \
🏢 Create a Subnet for private -> vpc-aws-private-subnet \
🆔 VPC ID -> select the vps-aws-ec2 \
🌏 Availability Zone -> Asia Pacific/ap-south-1a \
🌐 IPv4 subnet CIDR block -> 10.0.1.0/24 \
🌐 Create internet gateway -> vpc-aws-igtw \
🔄 Attach it to VPC -> vpc-aws-ec2 \
🛣️ Create Route table -> vpc-aws-public-route \
🆚 Select VPC -> vpc-aws-ec2 \
🛣️ Create Route table -> vpc-aws-private-route \
🆚 Select VPC -> vpc-aws-ec2 \
🖱️ Click on vpc-aws-public-route -> select subnet associations -> edit subnet association -> add vpc-aws-public-subnet \
🔁 Repeat above step for vps-aws-private-route \
🖱️ Click on vpc-aws-public-route -> select route -> edit route -> add internet gateway -> vpc-aws-igtw \
🌐 Select NAT gateways -> create NAT gateway -> vpc-aws-NAT -> select vpc-aws-public-subnet -> select public -> Allocate Elastic IP. \
🛣️ Select Route table -> vpc-aws-private-route -> edit route -> select NAT -> vpc-aws-NAT \
🏢 Create an EC2 instance -> vpc-aws-public-ec2 -> select vpc-aws-ec2 -> select subnet vpc-aws-public-subnet -> Enable Auto-assign public IP \
🏢 Create an EC2 instance -> vpc-aws-private-ec2 -> select vpc-aws-ec2 -> select subnet vpc-aws-private-subnet -> Disable Auto-assign public IP \
🚀 Try to perform SSH into vps-aws-private-ec2 from vps-aws-public-ec2 -> ping 0.0.0.0. \
    
    If you get the ping, your VPC is working perfectly! 🎉
