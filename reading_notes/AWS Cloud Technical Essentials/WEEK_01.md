**AWS Global Infrastructure**

1. Regions and Availability Zones.
    - Regions: geographic locations worldwide where AWS hosts its data centers.
        - Examples: us-east-1 (Northern Virginia) and us-east-2 (Ohio).
        - Regions are independent, no data is replicated in different regions without explicit consent and
          authorization.
        - Consider `Latency`, `Price`, `Service availability` and `Data compliance` when deciding which region to use.
    - Availability Zones (AZ): data centers with redundant `power`, `networking`, and `connectivity` located inside a
      region.
        - Examples: us-east-1a (AZ a in us-east-1) and us-east-1b (AZ b in us-east-1).
2. Different services can have the resources deployed at the level of an Availability Zone, Region or Globally.
    - Region-scoped service: when the user is only required to select the Region.
        - Data `durability` and `availability` is automatically performed by AWS.
    - AZ-scoped service: when the user is required select the AZ.
        - Data `durability` and `availability` is often the user responsibility.

**Interacting with AWS**

1. Action in AWS is an authenticated and authorized API call, that can be performed with:
    - AWS Management Console (Web).
    - AWS Command Line Interface (CLI).
    - AWS Software Development Kits (SDKs).

**Security and the AWS Shared Responsibility Model**

1. [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/).

**Protect the AWS Root User**

1. Authentication: identity verification.
2. Authorization: permission to access resources and services.
3. Access Keys: used for programmatic requests to AWS CLI or AWS API.
    - Access key ID: similar to username.
    - Secret access key: similar to password.
4. Root User: access to all services and resources.
    - Use a strong password.
    - Delete all access keys.
    - Do not use for administrative tasks or everyday tasks.
    - Enable MFA.

**Introduction to AWS Identity and Access Management**

1. IAM service manges account and resources access.
    - Global-scoped.
    - Share access without having to share access keys or passwords.
    - Select which actions and which resources that can be accessed.
    - Integrated with many AWS services by default.
    - Establish password policies and mandatory rotation periods.
    - Supports identity federation.
    - Offers no additional charges.
2. IAM User:
    - Person or Service that interacts with AWS.
    - Activities done by the IAM user is billed to the Root User account.
3. IAM Group:
    - Is a collection of users that inherit the permissions assigned to the group.
    - Give permissions to multiple users at once.
    - Groups can have many users.
    - Users can belong to many groups.
    - Groups cannot belong to groups.
4. IAM Policy:
    - Manage access and provide permissions to AWS services and resources.
    - Attached to IAM users, groups and roles.
    - Major elements:
        - Version: version of the policy language.
        - Effect: allow or deny access.
        - Action: action that should be allowed or denied.
        - Resource: objects that the policy statement covers.
        - [Access Policies Examples](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html).

**Role Based Access in AWS**

1. Principle of Least Privilege: grant only the necessary permissions.
2. IAM Roles When Possible: credentials are dynamically provided and expire after a defined period of time (15min/3h).
3. Identity Provider (IdP): use IAM roles to provide permissions to identities.
4. AWS SSO: IdP that lets users sign in to a user portal with a single set of credentials, that provides access to all
   assigned accounts and applications in one central location.
    - Is possible sync users and groups of a third-party IdP to AWS SSO.
