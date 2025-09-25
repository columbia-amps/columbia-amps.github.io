# AMPS Website

Site updates and edits happen directly here on GitHub; [GitHub Pages](https://docs.github.com/en/pages) deploys automatically.

## Quick Links
- Live site: https://columbia-amps.github.io/
- Homepage: `index.html`
- News: `_posts/` (Markdown files)
- Images: `assets/img/`
- Blog index: `/blog/` (rendered from `blog.html`)

---

## For Non-Technical Editors (no coding)

Everything is done in the GitHub web UI. Each commit publishes the site.

### Post news & updates (at `/blog/`)
1. Go to `_posts/`, **add file**, then **create new file**  
2. Name it `YYYY-MM-DD-<title>.md`  
3. Paste this snippet down below and edit:
   ```markdown
   ---
   layout: post
   title: "<post title>"
   date: <date in YYYY-MM-DD>
   ---

   Write your post here in Markdown format.
   - Add bullets
   - Links: [Columbia AMPS](https://<example link>.edu)
   - Image (upload first to `assets/img/`):
     ![Panel photo](/assets/img/<image name>.jpg)
   ```
* For information on Markdown format, this is a [helpful resource](https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet).
  
4. Commit changes. If you need support with GitHub operations, follow this [guide](https://training.github.com/downloads/github-git-cheat-sheet/) (or ask for help).

### Update different sections
#### Board:
In `index.html`, find the **Board** section and edit names/roles/emails.
* For uploading headshots, upload them as `assets/img/board/` and update `src` with that same path in `index.html`.

#### Events:
In `index.html`, find **Events** and edit the list items:
  ```html
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Coffee Chat with Alumni
    <span class="badge text-bg-primary">Oct 5, 2025 · 4:00 PM</span>
  </li>
  ```
* You can also paste a calendar embed URL into the commented `<iframe>` in the Events section!

#### Resources:
In `index.html`, find **Helpful Resources**, edit link text + URLs.

### Uploading images
* Put images in `assets/img/`
* Reference them as `/assets/img/<the image>.jpg`.



*(Don't forget to commit & push all changes!)*

---

## For Developers / Technical Maintainers
This is a static Bootstrap 5 homepage + Jekyll blog on GitHub Pages (no Node build and no custom plugins beyond jekyll-feed; the content is plain HTML/Markdown).

### File Structure
```
├─ index.html               # homepage
├─ _config.yml              
├─ blog.html         
├─ feed.xml           
├─ _posts/                  # news
│  └─ YYYY-MM-DD-title.md
├─ _layouts/
│  ├─ blog.html       
│  └─ post.html           
├─ _includes/
│  ├─ head.html            
│  ├─ footer.html          
│  └─ blog-index.html     
└─ assets/
   ├─ css/                  # custom CSS
   ├─ js/                   # custom JS
   └─ img/                  # images (board photos, etc.)
```

---

### GitHub Pages setup
1. Push the repo to GitHub (e.g., `columbia-amps/columbia-amps.github.io`).
2. Deploy from a branch (Settings/pages/source) (e.g., `main`).
3. Set the production URL in `_config.yml`:
   ```yml
   url: "https://columbia-amps.github.io"
   baseurl: ""      # kept empty for org/user pages
   ```

### Local preview via bundle exec jekyll serve (optional)
You don’t need this to edit but it's helpful for previewing changes locally. 

```bash
brew install ruby

gem install bundler jekyll

# a Gemfile was created in this repo
bundler add webrick
# you may need to run `sudo gem install commonmarker -v '0.23.12' --source 'https://rubygems.org/'`
bundle install

bundle exec jekyll serve
```

*Note:* Sometimes mac has errors with writing to the system Ruby. In this case, we suggest using Docker to run Jekyll.
1. Install [Docker desktop](https://docs.docker.com/desktop/setup/install/mac-install/)
2. Run `npm run dev`


**Final step:** Navigate to http://localhost:4000/ to view the site!

---
*For AMPS members with any questions (e.g., adding content, editing the site, or deployment), contact jss2326@columbia.edu or send a message via Slack.*
