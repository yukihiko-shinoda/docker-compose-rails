# docker-compose-rails

Docker Compose for Rails

<!-- markdownlint-disable no-trailing-punctuation -->
## How to create new Rails app?
<!-- markdownlint-enable no-trailing-punctuation -->

1\.
Enter into container:

```console
docker-compose run rails bash
```

2\.
Create gemfile:

```console
bundle init
```

3\.
Add rails into Gemfile:

```console
bundie add rails
```

4\.
Install gems:

```console
bundle install
```

Then, go to [How to install existing Rails app?](how-to-install-existing-rails-app)

5\.
Create new Rails project:

```console
rails new --database=mysql rails-hello-world
```

note:

--database Default: sqlite3

When use Rails 6 or later,
Git local repository and .gitignore automaticaly created.

cf.
- [第1章 ゼロからデプロイまで - Railsチュートリアル](https://railstutorial.jp/chapters/beginning?version=6.0#sec-the_hello_application)
- [Rails をはじめよう - Railsガイド](https://railsguides.jp/getting_started.html#%E3%83%96%E3%83%AD%E3%82%B0%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B)

6\.
Set `rails-hello-world/config/database.yml`:

```yaml

```

<!-- markdownlint-disable no-trailing-punctuation -->
## How to run existing Rails app?
<!-- markdownlint-enable no-trailing-punctuation -->

1\.
Set `.env` file:

```ini
PATH_TO_PROJECT=./rails-hello-world
```

2\.
Up containers:

```console
docker-compose up -d
```
