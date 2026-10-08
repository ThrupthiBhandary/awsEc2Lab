# AWS EC2 – Instance Creation and Connection

## Aim

To create an Amazon EC2 instance and connect to it using **EC2 Instance Connect**.

## Service Used

- Amazon EC2

## Requirements

- AWS Account
- Internet Connection
- Web Browser

## Procedure

### Step 1: Open Amazon EC2

1. Log in to the **AWS Management Console**.
2. Search for **EC2**.
3. Open the **EC2 Dashboard**.
4. Click **Launch Instance**.

### Step 2: Configure the EC2 Instance

1. Enter a suitable **Name** for the instance.
2. Select **Amazon Linux 2023** as the AMI.
3. Select an appropriate instance type such as **t2.micro** or **t3.micro**.
4. Select or create a **Key Pair** if required.
5. Configure the network settings.

### Step 3: Configure Security Group

Allow the following inbound rule:

| Type | Port | Source |
|---|---:|---|
| SSH | 22 | My IP |

> Port 22 is required for EC2 Instance Connect because the browser-based connection uses SSH in the background.

6. Click **Launch Instance**.

### Step 4: Open the EC2 Instance

1. Go to **EC2 → Instances**.
2. Select the newly created instance.
3. Wait until the **Instance State** shows `Running`.
4. Wait until the **Status Checks** show `2/2 checks passed`.

### Step 5: Connect Using EC2 Instance Connect

1. Select the running EC2 instance.
2. Click **Connect**.
3. Select the **EC2 Instance Connect** tab.
4. Keep the default username, usually:

```text
ec2-user
```

5. Click **Connect**.

### Step 6: Verify the Connection

A terminal will open in the browser.

Run:

```bash
whoami
```

Expected output:

```text
ec2-user
```

You can also check the operating system:

```bash
cat /etc/os-release
```

## Result

The Amazon EC2 instance was successfully created and connected using **EC2 Instance Connect** through the AWS Management Console.

## Conclusion

An Amazon EC2 instance was successfully launched and accessed through the browser-based **EC2 Instance Connect** feature without manually using an SSH command or `.pem` key file.
