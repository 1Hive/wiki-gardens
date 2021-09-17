# Include Your Metadata

Now that you have deployed a new Garden on-chain you should add your own data and assets to the Gardens website. To do it, create a PR in the [`dao-list` repository](https://github.com/1Hive/dao-list).

You need to add your Garden details on the `<network>.json` file depending of the network your Garden was deployed. The format of the data you need to include looks as follows:

```javascript
{
    "address": "0x8ccbeab14b5ac4a431fffc39f4bec4089020a155",
    "name": "1Hive",
    "description": "A sufficiently decentralized, self-improving system, limited only by our community's collective imagination.",
    "token_logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/1Hive/nativeToken.png",
    "logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/1Hive/logo.png",
    "logo_type": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/1Hive/logo_type.png",
    "wiki": "https://1hive.gitbook.io/1hive/",
    "forum": "https://forum.1hive.org/",
    "links": {
      "community": [
        {
          "label": "Discord",
          "link": "https://discord.gg/4fm7pgB"
        },
        {
          "label": "Github",
          "link": "https://github.com/1Hive"
        },
        {
          "label": "Twitter",
          "link": "https://twitter.com/1HiveOrg"
        },
        {
          "label": "Telegram",
          "link": "https://t.me/honeyswapdex"
        },
        {
          "label": "Forum",
          "link": "https://forum.1hive.org/"
        }
      ],
      "documentation": [
        {
          "label": "Wiki",
          "link": "https://wiki.1hive.org/"
        },
        {
          "label": "Bug Bounty",
          "link": "https://wiki.1hive.org/community/security/bug-bounty"
        },
        {
          "label": "FAQs",
          "link": "https://wiki.1hive.org/guides/faq"
        }
      ]
    }
    },
```

Where:

* **Address:** `Gardens DAO` address showed during the deployment script execution.
* **Name**: `Garden DAO` name.
* **Descriptions**: a brief description of the community.
* **TokenLogo**:  an optional asset to display the token symbol logo.
* **Wrappable token:** an optional asset of \`Boboli GArd`oboli Gardens` to display the token symbol logo.
* **Logo:** an optional asset to display the community logo.
* **LogoType:** an optional asset used in the header, to display the community logotype.
* **Forum**: an optional link to the forum where proposals will be discussed. Defaults to [1Hive forum](https://forum.1hive.org).
* **Wiki**: an optional link to the community wiki that will be displayed on the header.
* **Links:** list of links to display in the footer of the Garden home screen.
* **Documentation:** list of documentation resources to display in the footer of the Garden home screen.

Optionally you can place your assets under the directory: [`assets/<garden-name>`](https://github.com/1Hive/dao-list/tree/master/assets).

