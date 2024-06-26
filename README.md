# Tikalyzer Flask Service

API for TikTok analyzing service

<br/>

## 💻 Tech Stack

**Server:** Sure, it's Flask

<br/>


## 🏃‍♂️ Run Locally

First, open TikTok on your browser and login so that the code can get your msToken. [https://www.tiktok.com]

Clone the project

```bash
  git clone https://github.com/lhphat02/tikalyzer-flask-service
```

Go to the project directory

```bash
  cd tikalyzer-flask-service
```

Install dependencies

```bash
  pip install -r requirements.txt
```

Start the server

```bash
  flask run
```

<br/>

## 🚀 Installation and Set up for TikTok-API library

Initially install with pip

```bash
    pip install TikTokApi
    python -m playwright install

```

Now if a small adjustment for your TikTok-API library so that it can works normally:

1. Go to `.venv/Lib/TikTokApi/api/user.py` or by `Crtl + Click` to the `user.videos()` method in `app/service/crawl/get_user_videos.py` in VSCode.

2. Then go to line 188 in which the code looks like this:

```
    found = 0
    while found < count:
        params = {
            "secUid": self.sec_uid,
            "count": count,
            "cursor": cursor,
        }
```

3. Now change the `count` value to `35` like this:

```
    found = 0
    while found < count:
        params = {
            "secUid": self.sec_uid,
            "count": 35,
            "cursor": cursor,
        }
```

4. Voila, enjoy! Don't forget to `Ctrl + S`.

<br/>

## 📖 API Reference

#### Get insights of an user's videos

```http
  GET /api/userVideoInsights?user_name=${user_name}
```

| Parameter   | Type     | Description                              |
| :---------- | :------- | :--------------------------------------- |
| `user_name` | `string` | **Required**. username of TikTok channel |

#### Get insights of a hashtag's videos

```http
  GET /api/hashtagVideoInsights?hashtag=${hashtag}
```

| Parameter | Type     | Description                     |
| :-------- | :------- | :------------------------------ |
| `hashtag` | `string` | **Required**. hashtag on TikTok |

#### Get insights of trending videos

```http
  GET /api/trendingVideoInsights
```
