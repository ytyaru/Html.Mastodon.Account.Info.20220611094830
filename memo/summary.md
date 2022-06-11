# マストドンAPIからユーザのプロフィール情報を得る

## 結論

```sh
TOKEN=je-uamkBAD4th0p5UEfpqtJyqHYVIdlaMeVSipUrQXM
USERNAME=ytyaru
curl "https://mstdn.jp/api/v2/search?q=${USERNAME}&resolve=true&limit=5'" -H "Authorization: Bearer ${TOKEN}"
```

　整形するなら`jq`コマンドを使う。

```sh
TOKEN=je-uamkBAD4th0p5UEfpqtJyqHYVIdlaMeVSipUrQXM
USERNAME=ytyaru
curl "https://mstdn.jp/api/v2/search?q=${USERNAME}&resolve=true&limit=5'" -H "Authorization: Bearer ${TOKEN}" | jq .
```
```javascript
{
  "accounts": [
    {
      "id": "233143",
      "username": "ytyaru",
      "acct": "ytyaru",
      "display_name": "ytyaru",
      "locked": false,
      "bot": false,
      "discoverable": true,
      "group": false,
      "created_at": "2017-05-23T00:00:00.000Z",
      "note": "<p>趣味プログラマ。ラズパイ好き。モナコインやってます。<br />C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。</p><p><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">ytyaru.github.io/</span><span class=\"invisible\"></span></a><br /><a href=\"http://ytyaru.hatenablog.com/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">http://</span><span class=\"\">ytyaru.hatenablog.com/</span><span class=\"invisible\"></span></a><br /><a href=\"https://github.com/ytyaru\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">github.com/ytyaru</span><span class=\"invisible\"></span></a><br /><a href=\"https://twitter.com/ytyaru1\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">twitter.com/ytyaru1</span><span class=\"invisible\"></span></a></p>",
      "url": "https://mstdn.jp/@ytyaru",
      "avatar": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
      "avatar_static": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
      "header": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
      "header_static": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
      "followers_count": 17,
      "following_count": 0,
      "statuses_count": 392,
      "last_status_at": "2022-06-03",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108354515796494700",
      "username": "ytyaru_webmention",
      "acct": "ytyaru_webmention",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": null,
      "group": false,
      "created_at": "2022-05-24T00:00:00.000Z",
      "note": "<p></p>",
      "url": "https://mstdn.jp/@ytyaru_webmention",
      "avatar": "https://mstdn.jp/avatars/original/missing.png",
      "avatar_static": "https://mstdn.jp/avatars/original/missing.png",
      "header": "https://mstdn.jp/headers/original/missing.png",
      "header_static": "https://mstdn.jp/headers/original/missing.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 18,
      "last_status_at": "2022-06-10",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108440861062511279",
      "username": "ytyaru",
      "acct": "ytyaru@misskey.io",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": true,
      "group": false,
      "created_at": "2022-06-08T00:00:00.000Z",
      "note": "<p><span>趣味プログラマ。ラズパイ好き。モナコインやってます。<br>C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。<br></span><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\">https://ytyaru.github.io/</a></p>",
      "url": "https://misskey.io/@ytyaru",
      "avatar": "https://media.mstdn.jp/cache/accounts/avatars/108/440/861/062/511/279/original/f552cc12cbfbc87f.png",
      "avatar_static": "https://media.mstdn.jp/cache/accounts/avatars/108/440/861/062/511/279/original/f552cc12cbfbc87f.png",
      "header": "https://media.mstdn.jp/cache/accounts/headers/108/440/861/062/511/279/original/a857d7fb7eaf995d.png",
      "header_static": "https://media.mstdn.jp/cache/accounts/headers/108/440/861/062/511/279/original/a857d7fb7eaf995d.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 2,
      "last_status_at": "2022-06-08",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108441143307137401",
      "username": "ytyaru",
      "acct": "ytyaru@misskey.dev",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": false,
      "group": false,
      "created_at": "2022-06-08T00:00:00.000Z",
      "note": "<p><span>趣味プログラマ。ラズパイ好き。モナコインやってます。<br>C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。<br></span><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\">https://ytyaru.github.io/</a></p>",
      "url": "https://misskey.dev/@ytyaru",
      "avatar": "https://media.mstdn.jp/cache/accounts/avatars/108/441/143/307/137/401/original/1e4e747a02e35307.png",
      "avatar_static": "https://media.mstdn.jp/cache/accounts/avatars/108/441/143/307/137/401/original/1e4e747a02e35307.png",
      "header": "https://media.mstdn.jp/cache/accounts/headers/108/441/143/307/137/401/original/63110d66f4a2bcfc.png",
      "header_static": "https://media.mstdn.jp/cache/accounts/headers/108/441/143/307/137/401/original/63110d66f4a2bcfc.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 2,
      "last_status_at": "2022-06-08",
      "emojis": [],
      "fields": []
    }
  ],
  "statuses": [],
  "hashtags": [
    {
      "name": "ytyaru",
      "url": "https://mstdn.jp/tags/ytyaru",
      "history": [
        {
          "day": "1654905600",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654819200",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654732800",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654646400",
          "uses": "4",
          "accounts": "4"
        },
        {
          "day": "1654560000",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654473600",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654387200",
          "uses": "0",
          "accounts": "0"
        }
      ]
    }
  ]
}
```

* `api/v2/search` APIを使う
* JSON応答のうち`json.accounts`のオブジェクト配列から`acct`の値が検索文字列`q`と完全一致するものを対象とする
    * ユーザ名の後ろに`@ドメイン名`がついているものは他のサービスやインスタンスのアカウントである

　ユーザIDがわかっているときは以下URLでGETすればいいだけ。

```
https://mstdn.jp/api/v1/accounts/233143
```

```
{"id":"233143","username":"ytyaru","acct":"ytyaru","display_name":"ytyaru","locked":false,"bot":false,"discoverable":true,"group":false,"created_at":"2017-05-23T00:00:00.000Z","note":"\u003cp\u003e趣味プログラマ。ラズパイ好き。モナコインやってます。\u003cbr /\u003eC/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。\u003c/p\u003e\u003cp\u003e\u003ca href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"\u003e\u003cspan class=\"invisible\"\u003ehttps://\u003c/span\u003e\u003cspan class=\"\"\u003eytyaru.github.io/\u003c/span\u003e\u003cspan class=\"invisible\"\u003e\u003c/span\u003e\u003c/a\u003e\u003cbr /\u003e\u003ca href=\"http://ytyaru.hatenablog.com/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"\u003e\u003cspan class=\"invisible\"\u003ehttp://\u003c/span\u003e\u003cspan class=\"\"\u003eytyaru.hatenablog.com/\u003c/span\u003e\u003cspan class=\"invisible\"\u003e\u003c/span\u003e\u003c/a\u003e\u003cbr /\u003e\u003ca href=\"https://github.com/ytyaru\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"\u003e\u003cspan class=\"invisible\"\u003ehttps://\u003c/span\u003e\u003cspan class=\"\"\u003egithub.com/ytyaru\u003c/span\u003e\u003cspan class=\"invisible\"\u003e\u003c/span\u003e\u003c/a\u003e\u003cbr /\u003e\u003ca href=\"https://twitter.com/ytyaru1\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"\u003e\u003cspan class=\"invisible\"\u003ehttps://\u003c/span\u003e\u003cspan class=\"\"\u003etwitter.com/ytyaru1\u003c/span\u003e\u003cspan class=\"invisible\"\u003e\u003c/span\u003e\u003c/a\u003e\u003c/p\u003e","url":"https://mstdn.jp/@ytyaru","avatar":"https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png","avatar_static":"https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png","header":"https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png","header_static":"https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png","followers_count":17,"following_count":0,"statuses_count":392,"last_status_at":"2022-06-03","emojis":[],"fields":[]}
```

　ただ、どちらも認証したとき、そのユーザIDを取得できない。

## 過程

　APIリファレンスによると`api/v1/accounts/:id`によりプロフィール情報が取得できそうだ。

* https://docs.joinmastodon.org/methods/accounts/

```
https://mastodon.example/api/v1/accounts/:id
```

　ところが、`:id`がわからない。これはユーザ名ではなくユーザIDだ。数字だけで構成されている。はたしてこのユーザID、APIで取得できるのか？　できるなら、どうやるのか。

　残念なことに、認証したときユーザIDを返してくれない。認証したのにユーザ情報は得られない。そのために必要なユーザIDすら返されない。これは明らかにAPIの設計ミスと思われる。

　下記URLでは`/api/v1/accounts/verify_credentials`によってユーザIDが取得できるかのように言っているが、少なくとも現バージョンでは取得できない。

* https://qiita.com/KEINOS/items/c501bd433aa84d0d0108

```javascript
{"name":"xxxxx","website":null,"vapid_key":"xxxxxxxxxxxxxxxxxxxxxxx"}
```
 
　と思ったが、上記は`api/v1/apps/verify_credentials`だった。以下のように`api/v1/accounts/verify_credentials`すれば取得できた。

```sh
curl -X GET "https://mstdn.jp/api/v1/accounts/verify_credentials" -H "Authorization: Bearer ${TOKEN}"
```
```sh
{
  "id": "233143",
  "username": "ytyaru",
  "acct": "ytyaru",
  "display_name": "ytyaru",
  "locked": false,
  "bot": false,
  "discoverable": true,
  "group": false,
  "created_at": "2017-05-23T00:00:00.000Z",
  "note": "<p>趣味プログラマ。ラズパイ好き。モナコインやってます。<br />C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。<br />MEHCqJbgiNERCH3bRAtNSSD9uxPViEX1nu<br /><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">ytyaru.github.io/</span><span class=\"invisible\"></span></a><br /><a href=\"http://ytyaru.hatenablog.com/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">http://</span><span class=\"\">ytyaru.hatenablog.com/</span><span class=\"invisible\"></span></a><br /><a href=\"https://github.com/ytyaru\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">github.com/ytyaru</span><span class=\"invisible\"></span></a><br /><a href=\"https://twitter.com/ytyaru1\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">twitter.com/ytyaru1</span><span class=\"invisible\"></span></a></p>",
  "url": "https://mstdn.jp/@ytyaru",
  "avatar": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
  "avatar_static": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
  "header": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
  "header_static": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
  "followers_count": 17,
  "following_count": 0,
  "statuses_count": 392,
  "last_status_at": "2022-06-03",
  "source": {
    "privacy": "public",
    "sensitive": false,
    "language": null,
    "note": "趣味プログラマ。ラズパイ好き。モナコインやってます。\r\nC/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。\r\nMEHCqJbgiNERCH3bRAtNSSD9uxPViEX1nu\r\nhttps://ytyaru.github.io/\r\nhttp://ytyaru.hatenablog.com/\r\nhttps://github.com/ytyaru\r\nhttps://twitter.com/ytyaru1",
    "fields": [
      {
        "name": "モナコイン",
        "value": "MEHCqJbgiNERCH3bRAtNSSD9uxPViEX1nu",
        "verified_at": null
      }
    ],
    "follow_requests_count": 0
  },
  "emojis": [],
  "fields": [
    {
      "name": "モナコイン",
      "value": "MEHCqJbgiNERCH3bRAtNSSD9uxPViEX1nu",
      "verified_at": null
    }
  ]
}

```

　ググった所、以下のように`api/v2/search`を使うことで解決できそうだ。

* https://discourse.joinmastodon.org/t/how-to-get-mastodons-user-id-from-mastodon-account-acct-username-server/1658/7

　これでようやく`api/v1/accounts/:id`を実行できる。

　と思ったが、実行してみたところエラーになった。

　というか、`api/v2/search`によってプロフィール情報が取得できたので、もうこれでいいことにする。

　ついでに以下も参考情報としてメモっておく。なにやらユーザIDひとつだけでもバージョン差などにより色々とあるらしい。じつに面倒だ。

* https://www.antun.net/tips/api/mastodon.html

```sh
curl "https://mstdn.jp/api/v2/search?q=${USERNAME}&resolve=true&limit=5'" -H "Authorization: Bearer ${TOKEN}" | jq .
```
```javascript
{
  "accounts": [
    {
      "id": "233143",
      "username": "ytyaru",
      "acct": "ytyaru",
      "display_name": "ytyaru",
      "locked": false,
      "bot": false,
      "discoverable": true,
      "group": false,
      "created_at": "2017-05-23T00:00:00.000Z",
      "note": "<p>趣味プログラマ。ラズパイ好き。モナコインやってます。<br />C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。</p><p><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">ytyaru.github.io/</span><span class=\"invisible\"></span></a><br /><a href=\"http://ytyaru.hatenablog.com/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">http://</span><span class=\"\">ytyaru.hatenablog.com/</span><span class=\"invisible\"></span></a><br /><a href=\"https://github.com/ytyaru\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">github.com/ytyaru</span><span class=\"invisible\"></span></a><br /><a href=\"https://twitter.com/ytyaru1\" rel=\"nofollow noopener noreferrer\" target=\"_blank\"><span class=\"invisible\">https://</span><span class=\"\">twitter.com/ytyaru1</span><span class=\"invisible\"></span></a></p>",
      "url": "https://mstdn.jp/@ytyaru",
      "avatar": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
      "avatar_static": "https://media.mstdn.jp/accounts/avatars/000/233/143/original/86792d247a5ce9eb.png",
      "header": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
      "header_static": "https://media.mstdn.jp/accounts/headers/000/233/143/original/adf1f42e06de92ce.png",
      "followers_count": 17,
      "following_count": 0,
      "statuses_count": 392,
      "last_status_at": "2022-06-03",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108354515796494700",
      "username": "ytyaru_webmention",
      "acct": "ytyaru_webmention",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": null,
      "group": false,
      "created_at": "2022-05-24T00:00:00.000Z",
      "note": "<p></p>",
      "url": "https://mstdn.jp/@ytyaru_webmention",
      "avatar": "https://mstdn.jp/avatars/original/missing.png",
      "avatar_static": "https://mstdn.jp/avatars/original/missing.png",
      "header": "https://mstdn.jp/headers/original/missing.png",
      "header_static": "https://mstdn.jp/headers/original/missing.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 18,
      "last_status_at": "2022-06-10",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108440861062511279",
      "username": "ytyaru",
      "acct": "ytyaru@misskey.io",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": true,
      "group": false,
      "created_at": "2022-06-08T00:00:00.000Z",
      "note": "<p><span>趣味プログラマ。ラズパイ好き。モナコインやってます。<br>C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。<br></span><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\">https://ytyaru.github.io/</a></p>",
      "url": "https://misskey.io/@ytyaru",
      "avatar": "https://media.mstdn.jp/cache/accounts/avatars/108/440/861/062/511/279/original/f552cc12cbfbc87f.png",
      "avatar_static": "https://media.mstdn.jp/cache/accounts/avatars/108/440/861/062/511/279/original/f552cc12cbfbc87f.png",
      "header": "https://media.mstdn.jp/cache/accounts/headers/108/440/861/062/511/279/original/a857d7fb7eaf995d.png",
      "header_static": "https://media.mstdn.jp/cache/accounts/headers/108/440/861/062/511/279/original/a857d7fb7eaf995d.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 2,
      "last_status_at": "2022-06-08",
      "emojis": [],
      "fields": []
    },
    {
      "id": "108441143307137401",
      "username": "ytyaru",
      "acct": "ytyaru@misskey.dev",
      "display_name": "",
      "locked": false,
      "bot": false,
      "discoverable": false,
      "group": false,
      "created_at": "2022-06-08T00:00:00.000Z",
      "note": "<p><span>趣味プログラマ。ラズパイ好き。モナコインやってます。<br>C/C++, C#, Rust, Python, Bash, SQL, HTML/CSS/JavaScript等。<br></span><a href=\"https://ytyaru.github.io/\" rel=\"nofollow noopener noreferrer\" target=\"_blank\">https://ytyaru.github.io/</a></p>",
      "url": "https://misskey.dev/@ytyaru",
      "avatar": "https://media.mstdn.jp/cache/accounts/avatars/108/441/143/307/137/401/original/1e4e747a02e35307.png",
      "avatar_static": "https://media.mstdn.jp/cache/accounts/avatars/108/441/143/307/137/401/original/1e4e747a02e35307.png",
      "header": "https://media.mstdn.jp/cache/accounts/headers/108/441/143/307/137/401/original/63110d66f4a2bcfc.png",
      "header_static": "https://media.mstdn.jp/cache/accounts/headers/108/441/143/307/137/401/original/63110d66f4a2bcfc.png",
      "followers_count": 0,
      "following_count": 0,
      "statuses_count": 2,
      "last_status_at": "2022-06-08",
      "emojis": [],
      "fields": []
    }
  ],
  "statuses": [],
  "hashtags": [
    {
      "name": "ytyaru",
      "url": "https://mstdn.jp/tags/ytyaru",
      "history": [
        {
          "day": "1654905600",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654819200",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654732800",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654646400",
          "uses": "4",
          "accounts": "4"
        },
        {
          "day": "1654560000",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654473600",
          "uses": "0",
          "accounts": "0"
        },
        {
          "day": "1654387200",
          "uses": "0",
          "accounts": "0"
        }
      ]
    }
  ]
}
```

