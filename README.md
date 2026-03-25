# Phishing-Simulator


![img alt](https://github.com/HFHamdan/Phishing-Simulator/blob/main/gophish_logo.png)


## Overview

A controlled phishing attack simulation built using Gophish to study social engineering techniques, credential harvesting, and SOC detection strategies. The simulation was conducted in a local, isolated environment against a dummy account for educational purposes only.

## Tools & Setup

- Gophish (local installation)
- Gmail dummy target account
- Landing page template adapted from (https://github.com/trustedsec/social-engineer-toolkit/blob/master/src/html/templates/google/index.template) on GitHub

## Simulation Design

A two-step verification phishing email was crafted to create urgency around account security, prompting the target to verify their 2SV credentials via a fake login page. This mirrors a common real-world phishing pretext used to bypass user suspicion.

![img_alt](https://github.com/HFHamdan/Phishing-Simulator/blob/main/phishing_email.png?raw=true)

upon clicking the link it would lead you to this fake login page :

![img_alt](https://github.com/HFHamdan/Phishing-Simulator/blob/main/fake_login.png?raw=true)

## Campaign Results
The campaign successfully tracked the full attack timeline from email delivery, to open, to link click, to credential capture  as recorded in the Gophish dashboard. 

![img_alt](https://github.com/HFHamdan/Phishing-Simulator/blob/main/full_timeline.png?raw=true)

# SOC Detection & Response

## Incident/Finding Title: Phishing Campaign Simulation — Credential Harvesting
## Date: 24th/Mar/2026
Severity: High
Summary: A simulated phishing campaign was conducted using Gophish targeting one user via a fake two-step verification email. A credential harvesting landing page was used to capture credentials upon link click.
Indicators of Compromise (IOCs):

Sender email: redacted dummy email
Landing page URL: http://127.0.0.2/fake-login
Subject line / pretext: Two-step verification alert

Detection Opportunities:

Email gateway should flag mismatched or suspicious sender domain
URL inspection would reveal the landing page is not a legitimate Google domain
Proxy/DNS logs would show connection to suspicious URL
Email header analysis would expose spoofed or unusual sending infrastructure

Recommended Response:

Block sender domain
Reset credentials of any affected users immediately
Investigate whether credentials were used after capture
Conduct user awareness training focused on 2SV phishing pretexts

# Lessons Learned
Running this simulation highlighted how convincing a simple phishing pretext can be when combined with a legitimate-looking landing page. From a SOC perspective, the key detection opportunity lies in email header analysis and URL inspection before any user interaction occurs.
