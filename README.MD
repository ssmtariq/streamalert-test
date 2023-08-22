How to Deploy and Test
=======================
- Follow the [user guide](https://streamalert.io/) and additionally complete the following actions
- Update the `conf/global.json` file `account` section with your AWS Credentials
- Remove the statement `acl='log-delivery-write'` from `streamalert_cli/terraform/generate.py`
- Update `conf/outputs.json` with modifying existing `aws-sns`  element as below
  ```  
    "aws-sns": {
        "test-email": "streamalert-test-alerts"
      }
  ```
- **After deployment in AWS update every role the application created with an additional policy** `lambda:InvokeFunction` and others as required