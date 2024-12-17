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

# Getting Started

{% hint style="info" %}
This page discusses the express installation method of Novel. There are other installation methods available discussed in the [Installation](installation.md) page.
{% endhint %}

You are expected to know the basics of web development as well as working with Node.js, Next.js, React, and some database and UI design. The software will get you 90% of the way there, you will still need to perform some manual procedures and Novel will be there to help.

### Prerequisites

You will need to have the following software available in your development machine.

{% tabs %}
{% tab title="MacOS (OSX)" %}
* [ ] Git - git should already be available in OSX but if it isn't, head over to the [git downloads page](https://git-scm.com/download/mac) to get it.
* [ ] Node.js - we recommend installing Node.js via `nvm` which can be found in here.
* [ ] Docker - we use docker to automatically provision testing containers and controlling the database. [You can get it here.](https://www.docker.com/products/docker-desktop/)
* [ ] Stripe CLI - Stripe CLI is used to handle webhooks for localhost. [You can find it here.](https://docs.stripe.com/stripe-cli)
* [ ] Optional (Postgres) - If docker is not available in your machine, then you can install PostgreSQL via `brew` or [other methods discussed here](https://www.postgresql.org/download/macosx/).
* [ ] Optional (AWS CLI) - Is used for interacting with AWS services. You may need them if you use s3 or sqs or ec2. [You can download it here.](https://aws.amazon.com/cli/)
{% endtab %}

{% tab title="Windows" %}

{% endtab %}

{% tab title="Linux" %}



{% endtab %}
{% endtabs %}

Once you have purchased a license, the private github repository will be available to you. You can start by running these commands on your favorite terminal.

### Run development server

```sh
git clone https://github.com/madewithnovel/novel.git
cd novel
npm install
npm run dev
```

The `dev` command will automatically set up the required files and connections for you to as much as it can.&#x20;

<details>

<summary>Check Development Environment</summary>

Novel will perform diagnostics on the machine it is being run on and make sure that it can run without a problem.

The software will throw an error or at least a warning if the system running it is incompatible or cannot start fully.

</details>

<details>

<summary>Install Dependencies</summary>

Novel will run `npm install` if it hasnt been done already. It will also check 3rd party dependencies such as stripe, postgres, postmark and automatically set things up in the background if needed.

</details>

<details>

<summary>Check Configuration</summary>

Novel will automatically configure your system for development so that you can start writing code immediately.

It will also apply some sensible defaults that you can configure later on.

You will be asked to add the API keys from the 3rd-party software that Novel works with.

</details>

<details>

<summary>Set-up Database</summary>

Novel will set up the database and migrate the require tables automatically. This process also generates the relevant models and schemas that you can reuse in your code.

Remember that these models and schemas should not be modified directly and should be overridden in your application code instead. Learn about [Overriding Default Models](novel-server/database.md) here.

</details>

The steps above will require you to perform some manual intervention for 3rd-party software that Novel uses.

#### 1. Stripe

When you run `npm run dev` for the first time, it will open up the stripe dashboard and ask you to add your stripe keys into the .env file. You can find these keys in [dashboard.stripe.com/apikeys](https://dashboard.stripe.com/apikeys).

<figure><img src=".gitbook/assets/Screenshot 2024-04-16 at 4.14.02 PM.png" alt=""><figcaption></figcaption></figure>

Copy these keys over to your `.env` file or paste it into the CLI when requested.

```sh
STRIPE_PUBLIC_TOKEN=pk_test_***
STRIPE_API_TOKEN=sk_test_***
```

#### 2. Postmark

Postmark will also be needed for you to be able to send messages. Head over to [Setting up Postmark](guides/setting-up-postmark.md) for more information.

<figure><img src=".gitbook/assets/Screenshot 2024-04-16 at 4.16.25 PM.png" alt=""><figcaption></figcaption></figure>

Copy these keys over to your `.env` file or paste it into the CLI when requested.

<pre class="language-sh"><code class="lang-sh"><strong>POSTMARK_SERVER_TOKEN=423a***
</strong></code></pre>

### Configure Novel

...



### What's Next?

Your development server is now ready for you to start working on. Novel will hot-reload your API endpoints and any changes you have `/app` and `/web` so you dont have to start and restart the server.

Head on over to [Creating your first API endpoint](recipes/creating-a-new-api-route.md) to continue.
