# AMPS Website

Site updates and edits happen directly here on GitHub; [GitHub Pages](https://docs.github.com/en/pages) deploys automatically.

## Quick Links
- Live site: https://columbia-amps.github.io/
- Homepage: `index.html`
- News: `_posts/` (Markdown files)
- Images: `assets/img/`
- Blog index: `/blog/` (rendered from `blog.html`)

---

## How to Edit the Site for Non-Technical Editors (no coding)

1. **Clone the repo** (you only have to do this once)
      * Download VSCode
      * Open the columbia-amps repo
      * Run `git clone https://github.com/columbia-amps/columbia-amps.github.io.git`
2. To update site content, make edits to any of the text on `index.html`
   * To make changes to the actual site, you will need to use HTML / CSS (this is the same for making changes to the original AMPS site)
3. **Publish / push changes** - each push makes your change appear on the actual site

In the terminal you are using to access the repo, run these 3 commands:
```
git add
git commit -m “<what your change is>”
git push
```
Done! You will see your new changes on https://columbia-amps.github.io/ 
* For information on Markdown format, this is a [helpful resource](https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet).
* If you need support with GitHub operations, follow this [guide](https://training.github.com/downloads/github-git-cheat-sheet/) (or ask for help).

### Update different sections
#### Board:
In `index.html`, find the **Board** section and edit names/roles/emails.
* For uploading headshots, upload them as `assets/img/board/` and update `src` with that same path in `index.html`.

#### Events:
* To edit the **Events Calendar** section, go to `calendar.html`. There is a calendar embed URL nested under `<iframe>`
* To edit the events on the homepage, navigate to `index.html`, find **Events**, and edit the list items

e.g., 
  ```html
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Coffee Chat with Alumni
    <span class="badge text-bg-primary">Oct 5, 2025 · 4:00 PM</span>
  </li>
  ```


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
2. Run `npm run dev` (you will see the localhost / LiveReloader link)


**Final step:** Navigate to http://localhost:4000/ to view the site!

---
*For AMPS members with any questions (e.g., adding content, editing the site, or deployment), contact jss2326@columbia.edu or send a message via Slack.*
