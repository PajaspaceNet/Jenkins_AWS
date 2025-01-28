Hi, short demo AWS and script in BASH , <br><br><br>

### Example Output
```
Hello, World! Jenkins is working!
```

---

![obrazek](https://github.com/user-attachments/assets/0e013691-78c5-4d0e-a015-90f19367ce2f)

---

## Jenkins Hello World Project

This is a simple demonstration project to showcase the functionality of Jenkins for continuous integration (CI). The project automatically builds and runs a basic script whenever changes are pushed to this repository.

### Features
- **Continuous Integration**: Jenkins automatically builds and runs the script when changes are detected in the repository.
- **Hello, World** Script: A basic shell script that outputs a friendly message.

### Prerequisites
- A running Jenkins instance configured to pull from this repository.
- GitHub integration with Jenkins for seamless builds.

### How It Works
1. **Jenkins Setup**:
   - Jenkins pulls the latest changes from the repository.
   - It executes the `hello.sh` script.
2. **hello.sh**:
   - Outputs:
     ```
     Hello, World! Jenkins is working!
     ```

### File Structure
```
.
├── hello.sh  # The script that outputs a Hello, World message.
└── README.md  # This file.
```

### How to Use
1. Clone the repository:
   ```
   git clone https://github.com/PajaspaceNet/Jenkins_AWS
   ```
2. Make changes and push them to the repository:
   ```
   git add .
   git commit -m "Your changes"
   git push origin main
   ```
3. Jenkins automatically builds and runs the updated script.

---



## Project Status: "STOPPED" on AWS

### Current Status
This project is currently **stopped (STOPPED)** on AWS to **reduce operational costs**. All related AWS resources (e.g., EC2 instances, databases, S3 storage) have been paused or scaled down.

### Reason
AWS charges for active resources (e.g., running EC2 instances, active RDS databases). To minimize costs, all unnecessary running services have been stopped. This decision does not impact data integrity or functionality when the project is restarted.

### How to Resume the Project
If the project needs to be resumed, follow these steps:
1. Log in to the AWS Management Console.
2. Locate the relevant resources (e.g., EC2 instances, RDS databases).
3. Restart the services:
   - **EC2 Instance:** Select the instance and click **Start Instance**.   
4. Verify that the application is functioning and accessible.








