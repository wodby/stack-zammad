# Zammad stack for Wodby

Zammad helpdesk with PostgreSQL, Redis, Memcached, Elasticsearch and an OpenSMTPD mail relay. Wodby routes HTTPS to Zammad's NGINX, which serves the web app, its API and its WebSocket connections.

Enter the administrator's email when creating an app. Wodby creates the first administrator during the first deploy, so Zammad's setup page is never open to visitors. Sign in with that email and the generated `admin_password` token. Then set your organization name and connect the mailboxes Zammad should turn into tickets.

Elasticsearch powers Zammad's search and can be disabled to save resources; Zammad then searches the database. Attachments are stored in PostgreSQL, so back up the database. Agent notifications go out through the OpenSMTPD relay. For reliable delivery, set your mail provider's SMTP server as Zammad's notification sender under **Admin > Channels > Email**.

Each Zammad process runs one replica. A new app takes a few minutes before its domain answers, while Zammad installs its database.

<!-- wodby:generated:start -->
<!-- wodby:generated:end -->
