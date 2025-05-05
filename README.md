Intro to Cloud Computing 2/2024 Test

1. Create EC2 and Connect via SSH
2. Create EC2 and Make The Simple Webpage
3. Create S3 Bucket with Public Permission
4. Create S3 Bucket with S3 Glacier Policies
5. Count the Input Text Using Lambda
6. Lambda Console Output Trigger S3 via Object Upload
7. EBS Volume Snapshot
8. Create and Connect EBS Volume to EC2
9. RDS Free Tier Create SQL Query
10. Create Read Replica from RDS Free Tier

Prerequesis
1. XXXX is the 4 last digits of student id
For Example 6609612178 -> 2178
2. YYYY is the Unique Student Key
3. You make sure that you use AWS Sandbox Environment



### Video Link Reference
1. Create EC2 and Connect via SSH

* ไปที่หน้า EC2 Dashboard บน AWS Management Console
* คลิก Launch Instance
* ตั้งค่าดังนี้:
  Name: ec21234 <br>
  AMI: เลือก Amazon Linux 2023 \n
  Instance type: t2.micro \n
  Key pair: เลือกหรือสร้าง key pair เพื่อใช้ SSH \n
  Network settings: \n
    เลือก VPC/Subnet ที่สามารถเข้าถึงอินเทอร์เน็ต \n
    เลือก Allow SSH from anywhere (0.0.0.0/0) (สำหรับ sandbox เท่านั้น) \n
* คลิก Launch Instance
* SSH เข้าไปใน instance
```ssh -i "your-key.pem" ec2-user@<Public-IP-of-EC2>```
* คำสั่ง Linux CLI พื้นฐานที่สามารถรัน
```uname -a```

https://github.com/user-attachments/assets/fa73deed-a8d6-47a5-9361-8f600896d7dc

2. Create EC2 and Make The Simple Webpage

https://github.com/user-attachments/assets/8d660343-f945-4455-8685-9ac4ff636026

3. Create S3 Bucket with Public Permission

https://github.com/user-attachments/assets/313631fc-ab1f-480d-be64-19d30cb4eef8

4. Create S3 Bucket with S3 Glacier Policies

https://github.com/user-attachments/assets/236052ed-a20d-41b7-be13-def227da9542

5. Count the Input Text Using Lambda

https://github.com/user-attachments/assets/242373f0-6f8e-45ec-851c-cd210cdd9ea0

6. Lambda Console Output Trigger S3 via Object Upload

https://github.com/user-attachments/assets/31a01e86-cdc7-446f-ae38-48e98f6c7e9d

7. EBS Volume Snapshot

https://github.com/user-attachments/assets/955f35d6-b872-46ec-a424-928b7c4eae0d

8. Create and Connect EBS Volume to EC2

https://github.com/user-attachments/assets/8b3459e4-4759-42a7-b8df-feb6c80ed462

9. RDS Free Tier Create SQL Query

https://github.com/user-attachments/assets/1ce22dfd-1f10-4652-b15e-69db34e01c9e

10. Create Read Replica from RDS Free Tier

https://github.com/user-attachments/assets/b6cacfe2-8fb7-4ff8-b5e6-51c2a2c702d7

