codejunkies
===========

Public blog of codejunkies
http://tazer.github.io/codejunkies/


# Remove the public folder to make room for the gh-pages subtree
rm -rf public

# Add the gh-pages branch of the repository. It will look like a folder named public
git subtree add --prefix public git@github.com:spencerlyon2/hugo_gh_blog.git gh-pages --squash

# Pull down the file we just committed. This helps avoid merge conflicts
git subtree pull --prefix=public

# Run hugo. Generated site will be placed in public directory (or omit -t ThemeName if you're not using a theme)
hugo -t ThemeName


# Add everything
git add -A

# Commit and push to master
git commit -m "Updating site" && git push origin master

# Push the public subtree to the gh-pages branch
git subtree push --prefix=public git@github.com:spencerlyon2/hugo_gh_blog.git gh-pages
