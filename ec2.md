# EC2

## Type of Instances (Billing)
-	On Demand
  - Allows you to pay a fixed rate by the hour (or by the second) with no commitment
-	Reserved
  - Provides you with a capacity reservation and offer a significant discount on the hourly charge for an instance
  - Contract Terms are 1 Year or 3 Year Terms
  - RESERVED INSTANCE MARKET
    - Platform that supports the sale of third-party and AWS customer’s unused Standard Reserved Instances
-	Scheduled Reserved Instances
  - Purchase reservations that recur on a daily, weekly or monthly basis with a specific start time and duration
  - One year term
  - You pay for the time that the instances are scheduled, even if you do not use them
-	Spot
  - Enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications have flexible start and end times
  - If your instance is terminated by AWS in the first instance hour, you will not be charged for it
-	Dedicated Hosts
  - Physical EC2 server dedicated for your use.
  - Can help reduce costs by allowing you to use your existing server-bound software licenses

## Type of instances (Power)
-	F – for FPGA
-	I – for IOPS
-	G – for Graphics
-	H – High disk Throughput
-	T – Cheap general purpose (T2 micro)
-	D – for Density
-	R – for RAM
-	M – Main choice for general purpose apps
-	C – for Compute
-	P – Graphics (Pics)
-	X – Extreme Memory
-	Z – Extreme Memory and CPU
-	A – Arm-based workloads
-	U – Bare Metal

## EC2 Placement Groups
-	Clustered Placement Group (Can’t span multiple Azs)
  - Low network latency & high network throughput
-	Spread Placement Group (Can span multiple Azs)
-	Name must be unique within your AWS Account
-	Only certain type of instances can be launched in a placement group (Compute Optimized, GPU, Memory Optimized, Storage Optimized)
-	It is recommended that you launch the same instance type for all the instances in a placement group
-	You can’t merge placement groups
-	You can’t move an existing instance into a placement group. You can create an AMI from your existing instance and then launch a new instance from the AMI into a placement group

## AUTO SCALING
-	Amazon EC2 Auto Scaling is a fully managed service designed to launch or terminate Amazon EC2 instances automatically to help ensure you have the correct number of Amazon EC2 instances available to handle the load for your application
-	Scalling cooldown
  - Warm Up 
    - The amount of time needed for the instances to contribute to the Auto Scaling Group instances (can be changed)
    - 300 seconds default
  - Example: Now a spike in traffic occurs, causing the CloudWatch alarm to fire. When it does, the Auto Scaling group launches an instance to help with the increase in demand. However, there's a problem: the instance takes a couple of minutes to launch. During that time, the CloudWatch alarm could continue to fire, causing the Auto Scaling group to launch another instance each time the alarm fires -> this will bring additional costs
-	You can configure SNS Notifications
-	Scheduled scaling (predictable load changes)
  - Based on date and time
-	Lifecycle hooks let you take action before an instance goes into service or before it gets terminated
-	When an impaired instance fails a health check, Amazon EC2 Auto Scaling automatically terminates it and replaces it with a new one

SITUATIONS
-	If you have an elastic ip address associated with an instance it doesn’t incure charges if the instance is running and it has only 1 elastic ip address associated with it
