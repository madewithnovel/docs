---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Installation

## Happy Path

You can install Novel via the following commands and it will walk you through the required settings, dependencies, and accounts you need to have to get Novel running.

{% code title="Linux / OSX" %}
```sh
curl -L "https://madewithnovel.com/install.sh" | bash
```
{% endcode %}

This will ask the following questions

...



## Manual Install

### Step 1: Install Node.js

...



### Step 2: Clone the Novel Repositories

...



### Step 3: Set-up Database

...



### Step 4: Get Vendor Credentials

#### 4.1 Stripe

#### 4.2 Sentry

#### 4.3 Postmark



### Step 5: Configure the Application

....

See [configuration.md](novel-server/configuration.md "mention") on what values can be modified and how the configuration model works.



### Step 6: Start the Server

...

```sh
novel dev
```



## Next Steps

Head on over to [getting-started.md](getting-started.md "mention") and build your new SaaS. Good Luck!

