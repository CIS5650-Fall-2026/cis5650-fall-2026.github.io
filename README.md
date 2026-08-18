# CIS 5650 GPU Programming and Architecture

This website uses Hydejack Starter Kit, a quicker, cleaner way to get started blogging with [Hydejack](https://hydejack.com/).

## Quick Start

### Running locally (Windows only)

1. Clone repository (git users), or [download] and unzip.
2. If you don't have Ruby, install from here: https://rubyinstaller.org/
3. Open terminal, `cd` into root directory (where `_config.yml` is located)
4. Install Bundler if you haven't: `gem install bundler`
5. Run `bundle install` [^1]
6. Run `bundle exec jekyll serve`
7. Open <http://localhost:4000/>

### GitHub Pages

1. Fork this repository.
2. Go to **Settings**, rename repository to `<your github username>.github.io` (without the `<` `>`)
3. Edit `_config.yml` (you can do this directly on GitHub)
    1. Change `url` to `https://<your github username>.github.io` (without the `<` `>`)
    2. Change `baseurl` to `''` (empty string)
    3. **Commit changes**.
4. Go to **Settings** again, look for **GitHub Pages**, set **Source** to **master branch**.
5. Click **Save** and wait for GitHub to set up your new blag.


## Rolling the site over to a new semester

After copying this repo to `cis5650-fall-<year>.github.io`, edit the **Semester** block at the top of [`_config.yml`](_config.yml):

| Key | What it feeds |
| --- | --- |
| `course_year` | Every `Fall <year>` string and derived link in the page content |
| `course_site_url` | `url` |
| `course_github_org` | Sidebar menu link, GitHub link on the home page |
| `course_title` | Home page `<h1>` and `<title>` |
| `course_forum_url` | Sidebar menu link, Ed Discussions link on the home page |
| `course_survey_url` | Student survey links on the home page |
| `course_description` / `course_tagline` | Meta description and sidebar tagline |

The rest of the site reads those values through YAML aliases (`*course_title`) inside `_config.yml` and through Liquid (`{{ site.course_year }}`) in `_pages/`. The "Previous Semesters" page generates its whole list from `course_year`, so it needs no edit.

One value cannot be templated: `social.github` in [`_data/authors.yml`](_data/authors.yml), because Jekyll does not run Liquid in data files. Update it alongside `course_github_org`.