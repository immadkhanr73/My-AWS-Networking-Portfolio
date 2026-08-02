<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up An AWS Account

**Project Link:** [View Project](http://nextwork.ai/projects/aws-account-setup)

**Author:** Immad Khan  
**Email:** immadkhanr73@gmail.com

---

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-account-setup_r6s1t7u3)

---

## Introducing Today's Project!

We are setting up an AWS account

### Key tools and concepts

Create an AWS account with root user credentials.

Enable billing alerts to prevent surprise charges.

Verify your identity.

Add multi-factor authentication to secure your root account.

### Challenges and wins

This project took me approximately 15 minutes because I spent a bit of extra time setting up and testing my authenticator app for MFA.

---

## Creating My AWS Account

We will be sign up AWS using our email address and enter a strong password for account creation.

### Understanding the root user

When you first sign up for an AWS account, the credentials (email and password) you enter during registration create the root user identity.

Think of the root user as the master key to a physical building. It has absolute, unrestricted administrative power to access every single service, resource, and billing setting within that account. Every AWS account has exactly one root user associated with it.

Prevent Unwanted Costs and Theft: If a malicious actor gains access to your root credentials, they can delete your entire setup, steal sensitive databases, or run up thousands of dollars in server costs (such as launching massive crypto-mining servers) on your linked credit card.

Unrestrictable Access: Unlike regular IAM users (whose permissions can be limited and customized), you cannot restrict the permissions of the root user. It always has full access to everything.

---

## Setting Up Billing and Payment

In this step, we will choose account plan, enter contact information and a payment method.

### Why AWS requires a payment method

AWS asks for your payment method for two main reasons:

1) They want to make sure you’re a real person (not a bot trying to get free cloud resources).

2) If you choose to go past your Free Tier limits, they need a way to charge for that extra usage.

---

## Completing Account Activation

You have added your payment method. Now you need to verify your identity and select a support plan to activate your account.

### Identity verification and support plan

I verified my identity by:

Select your Country code from the dropdown.
Enter your mobile phone number.
Click Send SMS.

The Basic plan is free and includes access to AWS documentation, forums, and AWS Trusted Advisor checks. It is more than enough for learning and personal projects.

---

## Enabling Free Tier Alerts

Log in to the AWS Console.

Navigate to Billing Preferences.

Enable Free Tier usage alerts

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-account-setup_j6k1l7m3)

### Why usage alerts matter

AWS will send you an email when your usage reaches 85% of a Free Tier limit. This gives you time to stop or adjust your usage before any charges apply. It is one of the simplest ways to protect yourself from surprise bills.

---

## Securing the Account with MFA

AWS shares a secret key with you via a QR code.

Your authenticator app scans it and combines this key with the current time using a protocol called TOTP.

This generates a unique 6-digit code that changes every 30 seconds. Since AWS has the same key and time, it matches your code to verify it's you.

How to Enable MFA:

1) Log into AWS, open the IAM Dashboard, and click Add MFA.

2) Choose Virtual MFA device as your device type.

3) Scan the displayed QR code with your phone's app.

4) Enter two consecutive 6-digit codes to sync the clocks, then click Register MFA.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-account-setup_e3f7g2h8)

---

---
