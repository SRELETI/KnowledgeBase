### Jira REST API

#### Overview

* The endpoints for jira api have the following format `<host>/rest/<api-name>/<api-number>/`. The `api-name` is `api` and `api-number` is `2`. A sample rest call to fetch a issue using `Basic Authentication`
```
curl -H "Authorization: Basic <Encoded username-password>" -H "Content-Type: application/json" https://<hostname>/rest/api/2/issue/SAAS-324`
```

#### Authentication

* A client can authenticate with JIRA REST API using three ways.
    * Basic Authentication
    * OAuth
    * Cookies

