# Include Your Metadata

Now that you have deployed a new Garden on-chain you should add your own data and assets to the Gardens website. To do it, create a PR in the [`dao-list` repository](https://github.com/1Hive/dao-list).

You need to add your Garden details on the `<network>.json` file depending on the network your Garden was deployed. The format of the data you need to include looks as follows:

```javascript
{
  "address": "0x02945Cf2FbCB01119F1B26503b42416b53aF703C",
  "name": "Agave",
  "description": "Agave is a lending protocol owned by the community. Unlocking defi primitives on xDAI.",
  "wrappableToken": {
    "logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/Agave/logo.png"
  },
  "logo": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/Agave/logo.png",
  "logo_type": "https://raw.githubusercontent.com/1Hive/dao-list/master/assets/Agave/logo_type.png",
  "forum":"https://forum.1hive.org/",
  "links": {
    "community": [
      {
        "label": "Discord",
        "link": "https://discord.gg/86eVaKfv2Z"
      },
      {
        "label": "Github",
        "link": "https://github.com/agave-dao"
      },
      {
        "label": "Twitter",
        "link": "https://twitter.com/Agave_lending"
      },
      {
        "label": "Telegram",
        "link": "https://t.me/Agave1Hive"
      },
      {
        "label": "Forum",
        "link": "https://forum.1hive.org/"
      }
    ],
    "documentation": [
      {
        "label": "FAQs",
        "link": "https://wiki.1hive.org/guides/agave-faq"
      }
    ]
  }
}
```

Where:

* **Address:** `Gardens DAO` address showed during the deployment script execution.
* **Name**: `Garden DAO` name.
* **Descriptions**: a brief description of the community.
* **TokenLogo**:  an optional asset to display the token logo of the Garden.
* **Wrappable token:** an optional asset for`Boboli Gardens`to display the pre-existing ERC-20 token logo.
* **Logo:** an optional asset to display the community logo.
* **LogoType:** an optional asset used in the header, to display the community logotype.
* **Forum**: an optional link to the forum where proposals will be discussed. Defaults to [1Hive forum](https://forum.1hive.org).
* **Wiki**: an optional link to the community wiki that will be displayed on the header.
* **Links:** list of links to display in the footer of the Garden home screen.
* **Documentation:** list of documentation resources to display in the footer of the Garden home screen.

Optionally you can place your assets under the directory: [`assets/<garden-name>`](https://github.com/1Hive/dao-list/tree/master/assets).

