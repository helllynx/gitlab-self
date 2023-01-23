# GitLab-License-Generator

Generator GitLab License For Self-Hosted/Private Instances.

Last tested: 15.3.2-ee

**THIS IS NOT A CRACK WHICH MEANS YOU CAN NOT USE IT DIRECTLY**

gitlab-rake "gitlab:password:reset[root]"

[nero@workpc GitLab-License-Generator]$ ./make.sh 
[*] Booting generator
[i] Using core library version 2.2.1
[*] Loading RSA keys...
[*] Building license...
[*] Calling export...

=====================================================
{
  "version": 1,
  "licensee": {
    "Name": "Tim Cook",
    "Company": "Apple Computer, Inc.",
    "Email": "tcook@apple.com"
  },
  "issued_at": "1976-04-01",
  "expires_at": "2500-04-01",
  "block_changes_at": "2500-04-01",
  "cloud_licensing_enabled": false,
  "offline_cloud_licensing_enabled": false,
  "auto_renew_enabled": false,
  "seat_reconciliation_enabled": false,
  "operational_metrics_enabled": false,
  "generated_from_customers_dot": false,
  "restrictions": {
    "plan": "ultimate",
    "active_user_count": 2147483647
  }
}
=====================================================
License is valid
=====================================================

[*] License generated successfully!
[*] License file: result.gitlab-license


