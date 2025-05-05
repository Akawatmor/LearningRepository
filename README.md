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
* ตั้งค่าดังนี้ -> <br>
  Name: ec21234 <br>
  AMI: เลือก Amazon Linux 2023 <br>
  Instance type: t2.micro <br>
  Key pair: เลือกหรือสร้าง key pair เพื่อใช้ SSH <br>
  Network settings: <br>
    เลือก VPC/Subnet ที่สามารถเข้าถึงอินเทอร์เน็ต <br>
    เลือก Allow SSH from anywhere (0.0.0.0/0) (สำหรับ sandbox เท่านั้น)
* คลิก Launch Instance
* SSH เข้าไปใน instance
```ssh -i "your-key.pem" ec2-user@<Public-IP-of-EC2>```
* คำสั่ง Linux CLI พื้นฐานที่สามารถรัน
```uname -a```

https://github.com/user-attachments/assets/fa73deed-a8d6-47a5-9361-8f600896d7dc

2. Create EC2 and Make The Simple Webpage
* สร้าง EC2 ใหม่ ตั้งตามนี้ -> <br>
AMI: Amazon Linux 2023<br>
Instance type: t2.micro<br>
User data:
```
#!/bin/bash
yum update -y
yum install -y httpd
systemctl enable httpd
systemctl start httpd
echo '<center><h1>This is xxxx instance with the code yyyy that runs the Apache Webserver!</h1></center>' > /var/www/html/index.html
systemctl reload httpd
```
ตั้ง Security Group: เปิด TCP Port 80 (HTTP) จาก 0.0.0.0/0
* หลังจาก EC2 รันเรียบร้อย เข้าเบราว์เซอร์และเปิด:
```http://<Public-IP>```

https://github.com/user-attachments/assets/8d660343-f945-4455-8685-9ac4ff636026

3. Create S3 Bucket with Public Permission
* ไปที่ S3 Console

* คลิก Create bucket ตั้งตามนี้ -> <br>
Bucket name: s31234 <br>
ยกเลิก Block all public access <br>
ACL เป็น User Managed
* คลิก Create
* อัปโหลดไฟล์ (เช่น test.html)
* หลังอัปโหลดเสร็จให้ คลิกไฟล์ → Permissions → Make public
* Copy Object URL และทดสอบเปิดผ่านเบราว์เซอร์

https://github.com/user-attachments/assets/313631fc-ab1f-480d-be64-19d30cb4eef8

4. Create S3 Bucket with S3 Glacier Policies
* ไปที่ S3 Console → Create bucket
Name: lambda1234 <br>
เปิด default settings ทั้งหมด
* เมื่อสร้างเสร็จ → คลิก bucket → Management → Lifecycle rule
* คลิก Create lifecycle rule ตั้งตามนี้
Name: MoveToGlacier <br>
Scope: Apply to all objects <br>
Transition to Glacier after: 30 days <br>
* Save

https://github.com/user-attachments/assets/236052ed-a20d-41b7-be13-def227da9542

5. Count the Input Text Using Lambda
* ไปที่ Lambda Console → Create function
Name: lambda1234 <br>
Runtime: Python 3.12 <br>
Permissions: Use existing role → เลือก LabRole <br>
* ใช้โค้ดนี้ใน Lambda editor:
```
def lambda_handler(event, context):
    input_text = event.get("text", "")
    return len(input_text)
```
* คลิก Deploy
* ทดสอบ:
คลิก Test → Create new test<br>
Event name: TestHello <br>
Event JSON:<br>
คัดลอกโค้ด
```
{
  "text": "Hello Ake"
}
```
คลิก Test → Output ควรเป็น 9

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

