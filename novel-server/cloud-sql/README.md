# Cloud SQL

Cloud SQL is an easy way to access your database using only your client. This approach is similar to GraphQL or PostgREST but instead of a proprietary query language, it uses JSON and knex.js/objection.js conventions.

{% hint style="warning" %}
Cloud SQL is not a direct replacement for GraphQL or PostgREST. If you have these technologies in place, please continue to use them.
{% endhint %}

CloudSQL works by exposing the tables and their downstream relationships through a REST API provided by Novel. The following features are available:

* SELECT and GRAPH SELECT
* INSERT and GRAPH INSERT
* DELETE with CASCADE
* UPDATE and GRAPH UPDATE
* ORDER, LIMIT, OFFSET
* SELECT FUNCTIONS: MAX, MIN, AVG, ETC...
* TRANSACTIONS

These features are enough for you to develop a fully functioning feature without ever touching server code.

If you require more features, head over to our feature request page.







