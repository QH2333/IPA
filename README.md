# IPA official website

This is the source repository of the website of Information & Photography Association (IPA).

The development was started by YilinChen in 2014 and postponed in 2015 for complicated reasons.

Luckily, the development has restarted, Issues and pull requests are welcome.

:)

## About deploying

**This guide assumes that you have installed and configured Ruby on Rails and PostgreSQL.**

**Manual creating the database for the website is needed.**

The code here includes no configuration for production.

If you've just cloned the repository, you need to run:

```bash
$ bundle install
$ (echo -e "SECRET_KEY_BASE=\c" && rake secret) >> .env
```

You have to add some secrets to the **`.env`** file.

Qiniu keys and database information are needed, format:

```
QINIU_ACCESS_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
QINIU_SECRET_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
DATABASE_NAME=YOURDATABASENAME
DATABASE_USERNAME=YOURUSERNAME
DATABASE_PASSWORD=YOURPASSWORD
```

Now you can finish initializing the databse:

```bash
$ rake db:migrate RAILS_ENV=production
$ rake assets:precompile RAILS_ENV=production
```

Or you just want to update, run:

```bash
$ git pull
$ bundle install
$ rake db:migrate RAILS_ENV=production
$ rake assets:precompile RAILS_ENV=production
```

And then restart your server.
