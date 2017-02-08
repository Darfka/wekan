# Wekan

[![Wekan chat][vanila_badge]][vanila_chat]

2017-02-08 News: All of Wefork is now merged and moved back to official
Wekan. Wefork will not accept any new issues and pull requests.
All development happens on Wekan.

[Wefork announcement and merging back][fork_announcement]

[![Wefork Build Status][travis_badge]][travis_status]

[Wefork FAQ][fork_faq]

[Translate Wekan at Transifex][translate_wekan]

Wekan is an open-source and collaborative kanban board application.

Whether you’re maintaining a personal todo list, planning your holidays with
some friends, or working in a team on your next revolutionary idea, Kanban
boards are an unbeatable tool to keep your things organized. They give you a
visual overview of the current state of your project, and make you productive by
allowing you to focus on the few items that matter the most.

Wekan supports most features you would expect of it including a real-time user
interface, import from Trello (on standalone Wekan), cards comments, checklists,
member assignations, customizable labels, closing lists, filtered views, and more.

SSO options like LDAP, passwordless email, SAML, GitHub and Google Auth are
already available on Sandstorm, not standalone Wekan. Sandstorm is now completely
Open Source, including server clustering.

Since Wekan is a free software, you don’t have to trust us with your data and can
install Wekan on your own computer or server. In fact we encourage you to do
that by providing one-click installation on various platforms.

## Roadmap

Upcoming Wekan App Development Platform will make possible
many use cases like kanban workflows, dependencies, gantt charts,
WIP limits, time tracking, managing website, Rocket.Chat support
and custom apps with themes by providing Teams/Organizations,
APIs, admin interface, custom fields, calendar view, time tracking,
vote on cards, move cards to another board and board templates.
Some of these don't even have feature requests in Wekan issues,
so we do need detailed descriptions, screenshots and links to
videos how these should work.

We are very welcoming to new developers and teams to submit new pull
requests to devel branch to make this Wekan App Development Platform possible
faster. By working directly with Wekan you get the benefit of active
maintenance and new features added by growing Wekan developer community.
Please see [Developer Documentation][dev_docs] to get started.

Roadmap is handled using [Wekan GitHub issues][wekan_issues].
If you don't see your feature request or use case there, please add it.

Newer [Wefork GitHub issues][wefork_issues] will be be moved to there also.


## Screenshots

[![Screenshot of Wekan][screenshot_wekan]][roadmap_wekan]

[![Screenshot of Wefork][screenshot_wefork]][roadmap_wefork]

Since Wekan is a free software, you don’t have to trust us with your data and can
install Wekan on your own computer or server. In fact we encourage you to do
that by providing one-click installation on various platforms.

## Supported Platforms

Automatic generated newest builds are available for Docker, and some others that
install directly from this repo. Automatic builds will be added later for more
platforms.

### Docker: [Docker image][docker_image], [Docs][docker_docs], [Docker Nginx proxy][docker_nginxproxy], [Docker Issue][docker_issue]

Docker example, running latest Wekan using docker-compose:

#### Running from remote dockerhub images
```
sudo docker-compose pull && sudo docker-compose up -d --no-build
```

#### Running from locally built dockerhub images
```
sudo docker-compose up -d --build
```

#### Running from locally built dockerhub images and modified `ARG` variables (not recommended)
```
echo 'NODE_VERSION=v6.6.0' >> .env && \
echo 'METEOR_RELEASE=1.4.2.3' >> .env && \
echo 'NPM_VERSION=4.1.2' >> .env && \
echo 'ARCHITECTURE=linux-x64' >> .env && \
echo 'SRC_PATH=./' >> .env && \
sudo docker-compose up -d --build
```

Docker example, running latest Wekan using docker run commands alone:
```
docker run -d --restart=always --name wekan-db mongo:3.2.11

docker run -d --restart=always --name wekan --link "wekan-db:db" -e "MONGO_URL=mongodb://db" -e "ROOT_URL=http://localhost:8080" -p 8080:80 mquandalle/wekan:latest
```

[Docker on SUSE Linux Enterprise Server 12 SP1][sles]

[Install from source][install_source]

[VirtualBox][virtualbox]

[Debian Wheezy 64bit][debian_wheezy]

[![Deploy][heroku_button]][heroku_deploy]
[![SignUp][indiehosters_button]][indiehosters_saas]
[![Deploy to Scalingo][scalingo_button]][scalingo_deploy]
[![Install on Cloudron][cloudron_button]][cloudron_install]
[![Try on Sandstorm][sandstorm_button]][sandstorm_appdemo]


## Upcoming Platforms

[Autoinstall script][autoinstall] based on [this issue][autoinstall_issue]

[Create Sandstorm .spk file from source][sandstorm_spk]

Email to work on already working Heroku: Use 3rd party
email like SendGrid, update process.env.MAIL_URL ,
change from email at Accounts.emailTeamplates.from ,
new file in server folder called smtp.js on code
`Meteor.startup(function () });` .
TODO: Test and find a way to use API keys instead.

Azure: Install from source. Azure endpoint needs to be added. Not tested yet.

OpenShift: Not tested yet.

Google Cloud: Needs info how to enable websockets.

## License

Wekan is released under the very permissive [MIT license](LICENSE), and made
with [Meteor](https://www.meteor.com).

[vanila_badge]: https://vanila.io/img/join-chat-button2.png
[vanila_chat]: https://chat.vanila.io/channel/wekan
[fork_faq]: https://github.com/wefork/wekan/wiki/FAQ
[fork_announcement]: https://github.com/wekan/wekan/issues/640#issuecomment-276383458
[screenshot_wekan]: http://i.imgur.com/cI4jW2h.png
[screenshot_wefork]: http://i.imgur.com/ShX2OTk.png
[roadmap_wekan]: http://try.wekan.io/b/MeSsFJaSqeuo9M6bs/wekan-roadmap
[roadmap_wefork]: https://wekan.indie.host/b/t2YaGmyXgNkppcFBq/wekan-fork-roadmap
[wekan_issues]: https://github.com/wekan/wekan/issues
[wefork_issues]: https://github.com/wefork/wekan/issues
[sandstorm_button]: https://img.shields.io/badge/try-Wekan%20on%20Sandstorm-783189.svg
[sandstorm_appdemo]: https://demo.sandstorm.io/appdemo/m86q05rdvj14yvn78ghaxynqz7u2svw6rnttptxx49g1785cdv1h
[docker_image]: https://hub.docker.com/r/mquandalle/wekan/
[heroku_button]: https://www.herokucdn.com/deploy/button.png
[heroku_deploy]: https://heroku.com/deploy?template=https://github.com/wefork/wekan/tree/master
[indiehosters_button]: https://indie.host/signup.png
[indiehosters_saas]: https://indiehosters.net/shop/product/wekan-20
[scalingo_button]: https://cdn.scalingo.com/deploy/button.svg
[scalingo_deploy]: https://my.scalingo.com/deploy?source=https://github.com/wefork/wekan#master
[cloudron_button]: https://cloudron.io/img/button.svg
[cloudron_install]: https://cloudron.io/button.html?app=io.wekan.cloudronapp
[debian_wheezy]: https://github.com/soohwa/sps/blob/master/example/docs/1/wekan.md
[travis_badge]: https://travis-ci.org/wefork/wekan.svg?branch=devel
[travis_status]: https://travis-ci.org/wefork/wekan
[install_source]: https://github.com/wefork/wekan/wiki/Install-from-source
[sles]: https://github.com/wekan/wekan/wiki/Install-Wekan-Docker-on-SUSE-Linux-Enterprise-Server-12-SP1
[virtualbox]: https://github.com/wekan/wekan/wiki/virtual-appliance
[sandstorm_spk]: https://github.com/wefork/wekan/issues/36
[docker_image]: https://hub.docker.com/r/mquandalle/wekan/
[docker_docs]: https://github.com/wefork/wekan/wiki/Docker
[docker_nginxproxy]: https://github.com/wefork/wekan/wiki/Docker-NginxProxy
[docker_issue]: https://github.com/wefork/wekan/issues/33
[translate_wekan]: https://www.transifex.com/wekan/wekan/
[autoinstall]: https://github.com/wefork/wekan-autoinstall
[autoinstall_issue]: https://github.com/anselal/wekan/issues/18
[dev_docs]: https://github.com/wekan/wekan/wiki/Developer-Documentation
