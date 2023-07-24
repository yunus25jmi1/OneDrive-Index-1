# OneDrive Index

Showcase, share, preview, and download files inside *your* OneDrive with onedrive-vercel-index -

- Completely free to host 💸
- Super fast ⚡ and responsive 💦
- Takes less than 15 minutes to setup ⏱️
- Highly customisable ⚒️

🍌 More importantly, we are pretty (●'◡'●)

## Features

<table>
  <tbody>
    <tr>
      <td>
        <a
          href="https://drive.swo.moe/Lecture%20and%20Coursework%20CS%20(BIT)/2019%20-%20%E5%A4%A7%E4%B8%89%E4%B8%8B%20-%20%E7%BC%96%E8%AF%91%E5%8E%9F%E7%90%86%E4%B8%8E%E8%AE%BE%E8%AE%A1/n1570.pdf"
          >👀 File preview</a
        >
      </td>
      <td>
        <a
          href="https://drive.swo.moe/%F0%9F%8D%87%20Wallpaper"
          >💠  List / Grid layouts</a
        >
      </td>
      <td>
        <a
          href="https://drive.swo.moe/%F0%9F%8D%A1%20Genshin%20PV/New%20version%20PV/TGA2021%E3%80%8A%E5%8E%9F%E7%A5%9E%E3%80%8B%E5%8F%82%E9%80%89%E8%A7%86%E9%A2%91.mp4"
          >🎥 Video and audio</a
        >
      </td>
    </tr>
    <tr>
      <td>PDF, EPUB, markdown, code, plain text</td>
      <td>For previewing images and documents with thumbnails</td>
      <td>mp4, mp3, ..., play online or with IINA, PotPlayer ... with subtitles!</td>
    </tr>
    <tr>
      <td>
        <a
          href="https://drive.swo.moe/Lecture%20and%20Coursework%20CS%20(BIT)/2017%20-%20%E5%A4%A7%E4%BA%8C%E4%B8%8A%20-%20%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84/1%20%E7%BB%AA%E8%AE%BA.pptx"
          >📄 Office preview</a
        >
      </td>
      <td><a href="https://drive.swo.moe/%F0%9F%A5%9F%20Some%20test%20files/Articles">📝 README.md preview</a></td>
      <td><a href="https://drive.swo.moe/%F0%9F%A5%9F%20Some%20test%20files/Imagenette">📑 Pagination</a></td>
    </tr>
    <tr>
      <td>docx, pptx, xlsx, ...</td>
      <td>Also renders code blocks, images with relative links, ...</td>
      <td>For folders with 200 or more items</td>
    </tr>
    <tr>
      <td><a href="https://drive.swo.moe/%F0%9F%8C%9E%20Private%20folder">🔒 Protected folders</a></td>
      <td><a href="https://drive.swo.moe/%F0%9F%8D%8A%20Weibo%20emotes/Source2">⏬ Multi-file download</a></td>
      <td>🔎 Native Search</td>
    </tr>
    <tr>
      <td>Password protected routes and files. <a href="https://ovi.swo.moe/docs/features/protected-folders">Details here</a></td>
      <td>
        Compress and download multiple files or folders.
        <a href="https://ovi.swo.moe/docs/features/multi-file-folder-download">Details here</a>
      </td>
      <td>
        Searching through your shared OneDrive files (with some caveats 🥺).
        <a href="https://ovi.swo.moe/docs/features/search-for-files-and-folders">Details here</a>
      </td>
    </tr>
  </tbody>
</table>

... and more:

- Streamlined deployment, without having to get your tokens manually anymore!
- Direct raw-file serving and hosting ...
- Full dark mode support, style and website customisations ...

# Using your own clientId and clientSecret (Must Do This)

## Client ID
1. Go Here: https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade
2. Login with your Microsoft account, select New registration.
3. Enter the Name for your blade app, my-onedrive-vercel-index for example.
4. Set Supported account types to:
``Accounts in any organizational directory (Any Azure AD directory - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)``
5. Set Redirect URI (optional) to Web (the multiselect dropdown) and ``http://localhost`` (the URL).
6. Click Register.
Your ``Application (client) ID`` is the ``clientId`` to appear in your api.config.js

## Client Secret (for generating obfuscatedClientSecret)
1. Your client secret needs to be generated manually:
2. Open Certificates & secrets panel.
3. Click New client secret.
4. Create a new secret with description client_secret.
5. Set Expires to Custom.
6. Change Start and End to the longest available time duration available.
7. Open API permissions, select Microsoft Graph, select Delegated permissions, and search for:
- User.Read (this should already be available)
- Files.Read.All
- offline_access
Select all three of them and click Add permissions.

## obfuscatedClientSecret
1. Copy client secret value
2. Obfuscate your client secret: https://ovi.swo.moe/docs/advanced#modify-configs-in-apiconfigjs
3. You should get an obfuscated client secret which looks like:
``U2FsdGVkX1830zo3/pFDqaBCVBb37iLw3WnBDWGF9GIB2f4apzv0roemp8Y+iIxI3Ih5ecyukqELQEGzZlYiWg==``
4. Replace the ``obfuscatedClientSecret`` with this value in api.config.js

# Deploy (Vercel)
0. Replace `clientId` and `obfuscatedClientSecret` in api.config.js with your own. [🤔 How?](https://github.com/TheFlashSpeedster/OneDrive-Index#using-your-own-clientid-and-clientsecret-must-do-this)
1. Change ``userPrincipleName`` in ``site.config.js`` to your Microsoft account email address.
2. Change ``baseDirectory`` in ``site.config.js`` to a folder under your OneDrive root directory.
3. Import to Vercel and add Upstash integration.
4. Trigger a redeploy, and profit. 🎉

# Modified By ➳⚡️𝔗𝔥𝔢 𝔉𝔩𝔞𝔰𝔥⚡️༻
