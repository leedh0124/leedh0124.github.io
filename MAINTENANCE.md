# Maintaining Dong Ho Lee's website

This repository serves <https://leedh0124.github.io> using Jekyll and the existing
Minimal Mistakes theme. The November 2026 refresh updates the personal content;
it does not migrate hosting or replace the theme.

## Where to edit

| Content                                          | File                           |
| ------------------------------------------------ | ------------------------------ |
| Homepage and featured research                   | `_pages/home.md`               |
| Biography, interests, opportunities              | `_pages/about.md`              |
| Experience, education, skills                    | `_pages/career.md`             |
| Project descriptions and code links              | `_pages/projects.md`           |
| Publication records                              | `_data/publications.yml`       |
| Publication page and earlier Korean publications | `_pages/publication.md`        |
| Name, sidebar, contact, footer, SEO              | `_config.yml`                  |
| Main navigation                                  | `_data/navigation.yml`         |
| Personal styling                                 | `_sass/_research-profile.scss` |
| Downloadable documents                           | `assets/files/`                |

Publication records appear on the publications page and, when `featured: true`,
on the homepage. Use `kind: preprint`, `journal`, or `conference`. Keep the
newest records first, use a unique `id`, and retain the full author order.
Separate a journal submission from an accepted publication. Avoid citation
counts unless you intend to maintain a dated snapshot.

When updating a page, set its `last_modified_at` to the actual review date.
Update project descriptions as well as publication metadata after acceptance.

## Documents

The **CV/Resume** menu opens `/cv/`, rendered by `_pages/cv.md`. The page
shows two links and one common update date. Edit `cv`, `resume`, and `updated`
in `_data/documents.yml` to change the document paths or shared date.

Set `updated` using `YYYY-MM-DD` when revising the documents. This date does
not change automatically when the website is rebuilt. Editing the data file
triggers a normal preview rebuild without restarting Jekyll.

- `Dong_Ho_Lee_Industry_Resume.pdf`: the currently approved one-page résumé.
- `Dong_Ho_Lee_Academic_CV.pdf`: the current full academic CV.
- `DongHoLee_CV_vsF.pdf`: a copy of the current academic CV at its old URL,
  retained so existing bookmarks keep working.

The PDF files are copies, not live references to the sibling `myCV` repository.
After editing and compiling the CVs there, copy the new PDFs here. Keep the two
academic CV copies synchronized. See `CONTENT_REVIEW.md` for the deferred résumé
corrections that were deliberately left unchanged during this website update.

## Local preview

### Permanent setup on this Mac

Configured November 6, 2026:

- **Ruby 3.3.10**, installed through Homebrew as `ruby@3.3`.
- **Bundler 2.7.1**, supplied with that Ruby installation.
- `~/.zprofile` and `~/.zshrc` select Homebrew Ruby automatically in new terminals.
- Project dependencies are installed in `vendor/bundle/`; Bundler remembers this
  location in the ignored `.bundle/config` file.

**Open a new VS Code terminal before using the commands below.** You no longer
need the temporary `GEM_HOME` and `PATH` export commands from the earlier setup.
A new terminal also clears the old temporary settings through the startup
configuration.

### Everyday editing

```sh
cd ~/Documents/leedh0124.github.io
bundle exec jekyll serve --safe --livereload --host 127.0.0.1 --port 4001
```

Open <http://127.0.0.1:4001>. Keep the terminal running while you edit.

- Save a source file to rebuild the site and refresh the browser automatically.
- Press **Ctrl+C** to stop the server.
- After editing `_config.yml`, stop and restart the server.
- Port 4001 lets you run your own preview alongside the agent's preview on port
  4000\. If port 4000 is free, you can use `--port 4000` instead.

For ordinary content edits, these are the only commands you need.

### Installing or restoring project dependencies

The dependencies are already installed. Run this again only after changing the
Gemfile or if Bundler reports missing gems:

```sh
cd ~/Documents/leedh0124.github.io
bundle install
```

If `.bundle/config` has been removed, restore the local dependency location first:

```sh
bundle config set --local path vendor/bundle
bundle install
```

The Gemfile pins Jekyll to the 3.10 series used by GitHub Pages. Generated files
and local dependencies are ignored by Git; do not commit `_site/`, `.bundle/`,
or `vendor/bundle/`.

### Compile without a preview server

```sh
bundle exec jekyll build --safe
```

This generates `_site/` and exits. It does not start a server or watch for edits.

For a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build --safe
```

### What the options mean

| Command or option       | Purpose                                                  |
| ----------------------- | -------------------------------------------------------- |
| `bundle exec`           | Run Jekyll with this project's dependency versions.      |
| `jekyll serve`          | Compile, serve a preview, and rebuild when files change. |
| `--livereload`          | Refresh the browser after each rebuild.                  |
| `--safe`                | Use Jekyll's safe-mode plugin restrictions.              |
| `--host 127.0.0.1`      | Make the preview available only on this computer.        |
| `--port 4001`           | Select the preview address's port.                       |
| `JEKYLL_ENV=production` | Render production-specific settings, such as analytics.  |

Earlier commands included `GEM_HOME=/private/tmp/dhl-website-gems` because they
used temporary dependencies. The permanent installation replaces that workflow.
The agent may use `--destination` to put generated output in a temporary folder;
your normal commands use `_site/`.

### Checking the setup

In a new terminal:

```sh
command -v ruby
ruby --version
bundle --version
bundle check
```

Ruby should resolve to `/opt/homebrew/opt/ruby@3.3/bin/ruby`, and `bundle check`
should report that the Gemfile's dependencies are satisfied. The startup files
only clear `GEM_HOME` / `GEM_PATH` values that point to the old temporary website
setup; they do not require you to set a custom gem home.

Check the homepage, Research, Publications, Experience, and About pages; verify
the download buttons, mobile navigation, project anchors, and external links.
The original blog remains available at `/blog/`, outside the main navigation.

## Publishing

Publish manually through GitHub Pages. Editing this checkout, running a local
preview, or making a local commit does not publish changes by itself. Pushing to
the configured publishing branch triggers the public update.

### 1. Confirm the GitHub Pages source

Open [repository Settings → Pages](https://github.com/leedh0124/leedh0124.github.io/settings/pages).
Under **Build and deployment**, use:

- **Source:** Deploy from a branch
- **Branch:** master
- **Folder:** /(root)

Click **Save** if you changed these settings. Saving can deploy the version
already on GitHub; the local edits are uploaded in step 3. These are the settings
for this checkout; confirm them in GitHub rather than assuming they are already
selected. The repository's default branch is `master`, and the personal website
source is at the root. The `docs/` directory contains the theme documentation.

The existing `_config.yml` already sets `url` to
`https://leedh0124.github.io` and leaves `baseurl` empty, as needed for this address.
GitHub builds the Jekyll source, so you do not need to upload `_site/` or create
a custom deployment workflow for this branch-based setup.

### 2. Check the site and review your changes

In a new terminal:

```sh
cd ~/Documents/leedh0124.github.io
git branch --show-current
JEKYLL_ENV=production bundle exec jekyll build --safe
git status --short
git diff
```

The branch should be `master`. Resolve any build errors before publishing, and
use the local preview above to check the pages and PDF downloads. `git diff`
shows changes to tracked files; also review the new files marked `??` by
`git status`. Generated output and local dependencies are ignored by Git.

### 3. Commit and push

If every changed and new file is intended for this update, stage and review them:

```sh
git add -A
git diff --cached --stat
git diff --cached
```

If only some files belong in this update, use `git add path/to/file` for those
files instead of `git add -A`. After reviewing the staged changes:

```sh
git commit -m "Update personal website"
git push origin master
```

The push is the publishing step once Pages is configured. If Git rejects the
push because the remote branch has newer commits, fetch and reconcile those
changes before retrying; do not force-push over them.

### 4. Verify the public update

Open the repository's [Actions tab](https://github.com/leedh0124/leedh0124.github.io/actions)
and check that the Pages build and deployment for your new commit succeeds.
GitHub runs a Pages workflow even with **Deploy from a branch** selected.
If it fails, open the failed job and read its build log.

Visit <https://leedh0124.github.io> and check the updated pages and both document
downloads. GitHub says publication can take up to 10 minutes after a push. If
the old version still appears after a successful deployment, try a hard refresh
or a private browser window.

For future updates, repeat steps 2–4; the Pages settings are a one-time setup.
Official references: [configuring the publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
and [viewing a published site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#viewing-your-published-site).
