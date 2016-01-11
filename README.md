### Check AWS CloudTrail Status

This BASH script checks the name and status of CloudTrail in all regions of your AWS account.

**Requirements:**

* The awscli `sudo pip install awscli`
* A valid profile in `~/.aws/config` or `${AWS_CONFIG_FILE}` with the appropriate API keys

**Usage:**

```
trail-chkr.sh -p <profile_name> [ -d ]

  -p  : profile name (in ~/.aws/config)
  -d  : (optional) delete trails
```  

**Output:**

```
./trail-chkr.sh -p eng

Checking us-east-1...
CloudTrail Name: eng-cloudtrail-logs-ue1
Enabled: True

Checking eu-west-1...
CloudTrail Name: eng-cloudtrail-logs-ew1
Enabled: True

Checking ap-northeast-1...
CloudTrail Name: eng-cloudtrail-logs-an1
Enabled: True

Checking us-west-1...
CloudTrail Name: eng-cloudtrail-logs-uw1
Enabled: True

Checking us-west-2...
CloudTrail Name: eng-cloudtrail-logs-uw2
Enabled: True

Checking ap-southeast-1...
CloudTrail Name: eng-cloudtrail-logs-as1
Enabled: True

Checking ap-southeast-2...
CloudTrail Name: eng-cloudtrail-logs-as2
Enabled: True

Checking sa-east-1...
Enabled: False

Happy trails!
```

**To Do:**

- [ ] Replace the REGIONS variable with a dynamic array. Build with the `aws ec2 describe-regions` command
