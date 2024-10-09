 

# Cross-Region Disaster Recovery with AWS

This project demonstrates a **Cross-Region Disaster Recovery** architecture using AWS services. The solution ensures data redundancy and high availability across multiple AWS regions by leveraging Amazon **RDS**, **Route 53**, and other services for automated failover in the event of an outage in the primary region.

## Project Overview

In this project, I designed a disaster recovery architecture that provides automatic failover from a primary AWS region to a secondary region. The setup ensures high availability, minimal downtime, and seamless failover for mission-critical applications.

### Key Features
- **Cross-Region Read Replica**: Implemented Amazon RDS MySQL cross-region read replicas for data redundancy.
- **Automatic DNS Failover**: Configured Amazon Route 53 to automatically switch DNS records to the secondary region in the event of a primary region failure.
- **Secrets Management**: Used AWS Secrets Manager to securely manage database credentials and ensure failover security.
- **Data Synchronization**: Ensured data is constantly synchronized between the primary and secondary regions to minimize data loss.

## Architecture

The architecture includes:
1. **Primary Region**: Contains the active **Amazon RDS MySQL** database and handles application traffic.
2. **Secondary Region**: Houses a read replica of the RDS database, ready to take over in case of failure in the primary region.
3. **Amazon Route 53**: Manages DNS and handles automatic failover by pointing traffic to the healthy region.
4. **AWS Secrets Manager**: Securely stores database credentials, making them accessible across regions during failover.


## AWS Services Used
- **Amazon RDS MySQL**: Provides a managed relational database with cross-region replication.
- **Amazon Route 53**: Configured for DNS management and automatic failover.
- **AWS Secrets Manager**: Manages database credentials securely across regions.
- **Amazon CloudWatch**: Monitors region health and triggers failover events.
- **Amazon SNS**: Sends notifications for failover events.

## How to Deploy
1. **Set up Amazon RDS** in the primary region and enable cross-region read replicas.
2. Configure **Route 53** for DNS failover by creating health checks and failover routing policies.
3. Use **Secrets Manager** to securely store database credentials and replicate them across regions.
4. Test failover by simulating a region failure and monitor the automatic DNS switch.

## Lessons Learned
- **Cross-Region Replication**: Ensures minimal data loss in the event of region failures by keeping data in sync.
- **Failover with Route 53**: Configuring health checks and failover routing policies in Route 53 simplifies disaster recovery.
- **Security with Secrets Manager**: Using AWS Secrets Manager ensures secure handling of sensitive information during failover.

## Next Steps
- Implement **AWS Lambda** for automated recovery processes post-failover.
- Add **CloudFront** to the architecture for global content delivery with built-in failover.
- Explore additional disaster recovery strategies such as **Pilot Light** and **Warm Standby**.

## Acknowledgments

This project was completed as part of the coursework in **Digital Cloud Training**. Bootcamp 

## Conclusion

This project highlights how to build a highly available, disaster-resilient architecture using AWS cross-region capabilities. By automating the failover process with Route 53 and replicating data with RDS MySQL, this architecture ensures minimal downtime and data loss during regional outages.

![Screenshot 2024-04-12 184753](https://github.com/user-attachments/assets/69741ac8-26c3-436c-a180-18643384eaba)
