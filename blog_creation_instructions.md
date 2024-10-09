# Create a new blog localy
hugo new site pingsquare-Blog

# change into the directory corresponding to that website
cd pingsquare-Blog

# Initialize Git, hence turning "pingSquare-education" into a local repository.
git init

# Clone the "hugo-theme-relearn" theme into the themes directory, adding it to your project as a Git submodule.
git submodule add https://github.com/binokochumolvarghese/lightbi-hugo themes/lightbi-hugo

# Update hugo config file hugo.toml
echo "theme = 'lightbi-hugo'" >> hugo.toml

# Copy the contents of "exampleSite" to the "content" folder in your website.
cp -R themes/lightbi-hugo/exampleSite/content/  content
cp -R themes/lightbi-hugo/exampleSite/layouts/ layouts

# create a workflow for the site to be moved to the remote repo
cp -R ../pingSquare-LLC/.github .

# compile the website
hugo

# push the site to the remote repository
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/ping-square/ping-square-Blog.github.io.git
git push -u origin main
git status
git add .
git commit -m "moving 'pingsquare-Blog' folder to the remote repo"
git push origin main
rm README.md
git status
git add .
git commit -m "removed README.md file"
git push origin main

# add a Subdomain in Github Pages
echo "Blog.ping-square.com" >> CNAME