My old blog migrated from Jekyll (which was in Ruby and I didn't understand) to Pelican.

# Log

## 2018-02-14

- reinstall on as per instructions below (but didn't need to do the git clone stuff since already there)

## 2018-01-12

- made directory and created a conda environment `pelican`
- pip installed `pelican` and `markdown`
- installed pelican as per http://docs.getpelican.com/en/stable/quickstart.html
- git cloned plugins and themes

  git clone --recursive https://github.com/getpelican/pelican-plugins
  git clone https://github.com/getpelican/pelican-themes.git

- copied the pelican-bootstrap3 theme
- copied the i18i18n_subsites plugin (as part of the setup instructions for the theme) https://github.com/getpelican/pelican-themes/tree/master/pelican-bootstrap3

- dropped all the old `layout: post` jekyll tags
- 