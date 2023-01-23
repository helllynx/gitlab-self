# GitLab-License-Generator

Go to container shell and change root password:
```bash
gitlab-rake "gitlab:password:reset[root]"
```


## license generation

Change user info in `license.rb` to yours:

```ruby
license.licensee = {
  "Name" => "Name",
  "Company" => "Company",
  "Email" => "example@gmail.com",
}
```

then run

```bash
ruby license.rb
```

put `license_key.pub` to container and copy 

```bash
cp -f license_key.pub /opt/gitlab/embedded/service/gitlab-rails/.license_encryption_key.pub
```

To change plan u need to fix file `/opt/gitlab/embedded/service/gitlab-rails/ee/app/models/license.rb`

```diff
--- /opt/gitlab/embedded/service/gitlab-rails/ee/app/models/license.rb
+++ /opt/gitlab/embedded/service/gitlab-rails/ee/app/models/license.rb
@@ -367,7 +367,7 @@
  end

  def plan
-    restricted_attr(:plan).presence || STARTER_PLAN
+    restricted_attr(:plan).presence || ULTIMATE_PLAN
  end

  def edition
```

Last step is reconfigurate gitlab, run inside gitlab container:

```bash
gitlab-ctl reconfigure
gitlab-ctl restart
```

## apply license

Add license
Go to `Admin > settings > general > scroll down to buttom > add license` and put `GitLabBV.gitlab-license` file. 

The end.

