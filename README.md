# aws-ebs-volume-encryption
![Alt text](image-url)

## 🔐 1. Encrypting Before Provisioning (New Instance)
![Alt text](image-url)
![Alt text](image-url)
This method encrypts the EC2 volume at the time of creating the instance.

Logged in to the AWS Management Console.

Opened the EC2 service and viewed the list of instances.

For new instances, I clicked Launch Instance, selected an Amazon Machine Image (AMI) (Amazon Linux 2), chose instance type (t2.micro), and in the Storage section, enabled “Encrypt this volume.”

Launched the instance with AWS KMS-managed encryption enabled by default.

For existing unencrypted instances, I stopped the running instance.

Opened Elastic Block Store → Volumes and selected the unencrypted root volume.

Created a snapshot of that volume.

After the snapshot was created, I copied the snapshot and enabled encryption during the copy process.

Created a new encrypted EBS volume from the encrypted snapshot.

Detached the old unencrypted volume from the instance.

Attached the new encrypted volume to the instance as /dev/xvda.

Restarted the instance and verified it was running properly with encryption enabled.

✅ Result:

![Alt text](image-url)

The existing EC2 instance was successfully converted to an encrypted one without losing data.
