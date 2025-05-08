# FUTURE_CS_02
# Credential Harvesting using Social Engineering Toolkit(Phishing Simulation)

## Overview

This guide outlines the steps to perform a credential harvesting attack by cloning a legitimate website (e.g., Google) using the Social Engineering Toolkit (SET). The attack involves creating a phishing email with a masked URL that redirects victims to a cloned website to capture their credentials. This README provides a detailed walkthrough, from setting up the attack to crafting and sending the phishing email, and includes tips on how to identify and protect against such attacks.

## Prerequisites

-   Kali Linux or a similar penetration testing distribution
-   Social Engineering Toolkit (SET)
-   Basic knowledge of networking and social engineering principles

## Steps

### 1. Setting Up the Attack Environment

1.  **Open the Social Engineering Toolkit**:
    -   Access SET from the Kali Linux menu by navigating to `Social Engineering Tools` -> `Social Engineering Toolkit`.
2.  **Enter Default Password**:
    -   If prompted, enter the default password for Kali.
3.  **Select Attack Options**:
    -   Choose `Social Engineering Attacks` (Option 1).
    -   Select `Website Attack Vectors` (Option 2).
    -   Pick `Credential Harvester Attack Method` (Option 3).
4.  **Choose a Method**:
    -   Select `Site Cloner` to clone any website or `Website Templates` for pre-made templates. In this example, we use `Website Templates`.
5.  **Enter IP Address**:
    -   Enter your machine's IP address to host the cloned site.
6.  **Select Website Template**:
    -   Choose the `Google` website template.

### 2. Testing the Cloned Website

1.  **Access the Cloned Site**:
    -   Open a web browser and enter your IP address. This should display the cloned Google website.
2.  **Enter Credentials**:
    -   Enter a test email and password on the cloned site.
3.  **Observe Capture**:
    -   Verify that the entered credentials (email and password) are captured by SET.
4.  **Redirection**:
    -   Note that the browser redirects back to the real Google site after submitting the credentials.

### 3. Crafting the Phishing Email

1.  **Create a New Google Account**:
    -   Create a new Google account with a non-suspicious name like "Support Alert" or "Account Technical Alert".
2.  **Create a Legitimate-Looking Username**:
    -   Use a username that appears legitimate, such as `systemdataprotection.alert@gmail.com`.
3.  **Set a Simple Password**:
    -   Set a simple password (e.g., `abcd1234`).
4.  **Enter a Recovery Email**:
    -   Enter your actual email address as the recovery email.
5.  **Copy Google Email Content**:
    -   Copy the entire content of a legitimate email from Google.

### 4. Sending the Phishing Email

1.  **Open Gmail in Kali**:
    -   Use the newly created email account to open Gmail in the Kali machine.
2.  **Compose a New Email**:
    -   Create a new email and paste the copied Google email content into it.
3.  **Modify the Email**:
    -   Change the recipient to the victim's email address.
    -   Change the sender name to something innocuous (e.g., "Jenny Holmes").
4.  **Modify Links**:
    -   Modify the links in the email to redirect to the credential harvesting website.

### 5. Masking the URL

1.  **Use an IP to Decimal Converter**:
    -   Use a tool like [dnshcheck.org/ip-to-decimal.php](http://dnshcheck.org/ip-to-decimal.php) to convert your IP address to its decimal equivalent.
2.  **Construct the Masked URL**:
    -   Create the URL with URL masking: `$http://www.google.com@decimal_ip$`
    -   The `@` symbol ensures everything after it is part of the actual link.
3.  **Replace Links in the Email**:
    -   Replace the original URLs in the email with the masked URL.

### 6. Finalizing the Phishing Email

1.  **Change URLs**:
    -   Ensure all URLs redirect to the credential harvesting website.
2.  **URL Hover Effect**:
    -   Modify the URLs so that hovering over them displays `$www.google.com$` with random characters, but still redirects to the malicious site.

## Demonstration

-   Firefox may show an alert, while Chrome might not. Clicking `yes` on Firefox will load the credential harvesting website.
-   The email should appear legitimate, with no typos or suspicious elements.

## Example Capture

-   If the victim enters their email and password, the credentials will be captured on your machine.

## Identifying Phishing Emails

-   **Sender's Email in Content**:
    -   Be cautious if the sender's own email address is mentioned within the email content.
-   **Generic Terms**:
    -   Watch out for emails using generic terms like "you" instead of a specific name.
-   **Misleading Links**:
    -   Even if the link appears legitimate (e.g., `google.com`), it could still be a phishing attempt.

## Protecting Yourself from Phishing

-   **Be Vigilant**:
    -   Stay alert when browsing the web and receiving emails.
-   **Change Passwords Regularly**:
    -   Update your passwords frequently across multiple sites.
-   **Avoid Password Reuse**:
    -   Do not use the same password for multiple accounts.

## Disclaimer

This information is for educational purposes only. Performing credential harvesting attacks without explicit permission is illegal and unethical. The intent of this guide is to raise awareness and educate on potential security threats.
