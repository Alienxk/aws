**Compute as a Service on AWS**

1. Types of compute: virtual machines, container services and serverless.

**Introduction to Amazon Elastic Compute Cloud**

1. Amazon EC2:
    - EC2 instance (Virtual Machine):
        - Instance Families:
            - General purpose: balance of compute, memory and networking resources.
            - Compute optimized: high-performance processors.
            - Memory optimized: large data sets in memory.
            - Accelerated computing: floating-point number calculations, graphics processing or data pattern matching.
            - Storage optimized: high sequential read and write access to large data sets on local storage.
        - Model `<family and generation number>.<capacity>`:
            - Example: `c5.large` (generic computation family and fifth generation large instance capacity).
        - EC2 Instance live inside a VPC (resources inside the default VPC are public and accessible by the internet).
        - Resides in an Availability Zone: use at least two instances in separate Availability Zones for high
          availability.
    - Amazon Machine Images (AMI): image that provides the information required to launch an instance.
        - Provided by AWS Marketplace.
        - Provided by Community AMIs.
        - Created from EC2 instances.
        - Built using EC2 Image Builder.
    - AMI ID: `ami-<unique ID to AWS region>`.

**Amazon EC2 Instance Lifecycle**

1. Pending state: preparing to enter the running state.
2. Running state (start charging): the instance is running.
3. Reboot the instance: equivalent to rebooting an OS.
    - Remains on the same host.
    - Maintains its private IP address.
    - Maintains its public IP address.
    - Maintains any instance stored data.
4. Stop (no charges will be made anymore) or start the instance:
    - May be placed on a new underlying physical server.
    - Maintains the same private IP address.
    - Gets a new public IP address.
    - Lose any instance stored data.
5. Stop-Hibernate (suspend-to-disk) the instance:
    - Saves the RAM content to the EBS root volume.
6. Terminate the instance:
    - Everything will be erased and lost.

**Pricing Options**

1. On-Demand Instances (Pay As You Go):
    - Pay for compute capacity without long-term commitments.
    - Begins when the instance is running.
    - Stops when the instance is stopped or terminated.
2. Reserved Instances (RIs):
    - Discount compared to On-Demand instance pricing.
    - Payment Options:
        - All Upfront: higher discount than Partial Upfront.
        - Partial Upfront: higher discount than No Upfront.
        - No Upfront: higher discount than On-Demand (you still pay for a stopped or terminated instance).
3. Spot Instances:
    - Up to a 90% discount compared to On-Demand.
    - Set a limit on how much to pay for the instance hour.
        - Get an instance if the amount to pay is more than the Spot price and there is capacity.
    - A spot instance may be interrupted if capacity is no longer available or the price exceeds willing to pay amount.
        - AWS will warn 2 minutes before interrupts the instance.

**Container Services on AWS**

<continue Reading 2.3>