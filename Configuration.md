### What can be configured and what are these configuration options?

The configuration file is located at [invidious/config/config.yml](https://github.com/omarroth/invidious/blob/master/config/config.yml).

`video_threads (default 0)` Number of threads to use for updating videos in cache (mostly non-functional)

`crawl_threads (default 0)` Number of threads to use for finding new videos from YouTube (used to populate "top" page)

`channel_threads (default 1)` Number of threads to use for crawling videos from channels (for updating subscriptions)

`feed_threads (default 1)` Number of threads to use for updating feeds (RSS Feeds)

```
db:
  user: kemal # your database user
  password: kemal # your database password
  host: localhost # database host
  port: 5432 # postgres port
```

`full_refresh (default false)` Used for crawling channels: threads should check all videos uploaded by a channel

`https_only (default false)` Used to tell Invidious it is accessed via https, set to `true` if you have for example a reverse proxy with a ssl certificate

`domain (default nil)` You should specify the domain you publish your Invidious instance here

`hmac_key (default nil)` Signing key for CSRF tokens and pubsub (randomly generated on startup, should be random string)

`use_pubsub_feeds (default false)` Support server-side notifications from YouTube using [PubSubHubbub](https://developers.google.com/youtube/v3/guides/push_notifications). Requires `domain` and `hmac_key` to be set

`default_home (default "Top")` Default home page

`feed_menu (default ["Popular", "Top", "Trending", "Subscriptions"])` Order of tabs on feed menu

`top_enabled (default true)` Whether top endpoints should be enabled (better for smaller instances)

`captcha_enabled (default true)` Determine if CAPTCHA should be required for login/registration

`login_enabled (default true)` Whether users should be able to login

`registration_enabled (default true)` Whether new users should be able to register

`statistics_enabled (default false)` Whether statistics should be available from `/api/v1/stats`

`admins (default [])` List of user IDs that have access to administrator preferences

`external_port (default nil)` Invidious should supply links to a different port (if running behind a proxy, for example). PubSub notifications (if enabled) will also be sent to this port