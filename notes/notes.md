# CloudWatch Monitoring Notes

## What I was trying to do

The goal here was to monitor an EC2 instance and get notified when CPU usage gets too high.

Instead of just setting it up, I wanted to actually test it and confirm that the alert works properly.

---

## How I set it up

I used CloudWatch to track CPU usage on my EC2 instance.

Then I created an alarm that:
- triggers when CPU goes above 70%
- checks twice before triggering (to avoid false alarms)
- sends an email using SNS

I also had to create an SNS topic and subscribe my email, then confirm it.

---

## Testing the setup

To test everything, I connected to the EC2 instance and ran:

```bash
yes > /dev/null &
