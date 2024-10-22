# Ansible role to setup a log shipper.

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Basic usage
You may use the simplified setup by overriding the defaults on `defaults/main.yml` like this, in a minimalistic setup
that uses an ElasticSearch endpoint:
```yaml
- name: install and configure journalbeat
  hosts: all
  roles: nholuong.journalbeat
  vars:
    journalbeat_elasticsearch: true
    journalbeat_hosts: { "logs.example.com:9200" }
```

Basically, to use the role you select an endpoint type (elasticsearch, logstash, kafka or redis), set the corresponding
variable to true and set the `journalbeat_hosts` variable to contain the endpoints' list that will have the logs
delivered to.

You also have easily available additional metadata that may be filled with useful information, like this:
```yaml
journalbeat_product: "webserver"
journalbeat_env: "production"
journalbeat_net: "dmz"
journalbeat_dc: "ny1"
```

## Advanced settings
If you need to setup any variable that isn't contained in the easy setup, you may define it in the `journalbeat_conf`
variable that holds a dict exactly the same as the YAML file used to configure the journalbeat daemon, and this
variable will be joined to the default configuration. Like this:
```yaml
journalbeat_conf:
  journalbeat:
    convert_to_numbers: false
  output:
    elasticsearch:
      path: "/somePath"
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
