# Publish `proteaguy.com` with GitHub Pages

These steps are written for launching the supplied static website without a command line.

## 1. Create the GitHub repository

1. Sign into the GitHub account that should own the website.
2. Create a new repository named `proteaguy-site`.
3. A **public** repository works with GitHub Pages on the free plan.
4. Do not initialize it with another README because this package already includes one.

## 2. Upload the website

1. Open the new repository.
2. Choose **Add file → Upload files**.
3. Unzip the website package on your computer.
4. Drag the **contents inside the folder** into GitHub—not the outer folder itself.
5. Confirm that `index.html`, `styles.css`, and `CNAME` appear at the top level.
6. Commit the upload to the `main` branch.

## 3. Turn on GitHub Pages

1. Open the repository’s **Settings**.
2. Select **Pages** in the sidebar.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select `main` and `/ (root)`.
5. Save.
6. Wait for GitHub to show the temporary `github.io` site address and open it to confirm the website works.

## 4. Add the custom domain in GitHub first

In the same **Settings → Pages** screen:

1. Enter `proteaguy.com` under **Custom domain**.
2. Save it before changing the GoDaddy DNS.

The supplied repository already contains a `CNAME` file, but the domain should still be entered in the repository’s Pages settings.

## 5. Change only the needed GoDaddy DNS records

In GoDaddy, open the DNS records for `proteaguy.com`.

Do **not** delete nameservers, MX records, email records, verification TXT records, or unrelated DNS entries. Only replace records that conflict with the website at `@` or `www`.

### Apex domain (`proteaguy.com`)

Create these four `A` records:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

Use GoDaddy’s default TTL unless there is a reason to change it.

### `www.proteaguy.com`

Create one CNAME record:

| Type | Name | Value |
|---|---|---|
| CNAME | www | `YOUR-GITHUB-USERNAME.github.io` |

Replace `YOUR-GITHUB-USERNAME` with the account that owns the repository.

Remove any existing parking or website-builder record that uses the same `@` or `www` host and conflicts with these values. Do not remove unrelated records.

## 6. Enable HTTPS

Return to **GitHub → Repository Settings → Pages**.

After GitHub recognizes the DNS configuration, select **Enforce HTTPS**. The option may remain unavailable while DNS and the certificate are still being prepared.

## 7. Recommended domain verification

GitHub recommends verifying the custom domain at the account level to reduce the risk of another GitHub user claiming it if the repository is ever disconnected.

GitHub will provide a unique TXT record. Add that exact TXT record in GoDaddy and leave it in place after verification.

## 8. Final checks

Open all four versions:

```text
https://proteaguy.com
https://www.proteaguy.com
http://proteaguy.com
http://www.proteaguy.com
```

They should resolve to the secure website. Also check:

- Mobile menu
- Email buttons
- Photographs and captions
- Spelling of Ben’s name and email
- No old GoDaddy placeholder page remains

## Important launch note

DNS changes are not always immediate. The temporary GitHub Pages address can still be used to show Ben the finished website while the custom domain finishes updating.

## Official references

- GitHub Pages publishing: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- Custom domain setup: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- Domain verification: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- HTTPS: https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
