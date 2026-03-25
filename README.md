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

![img_alt](
