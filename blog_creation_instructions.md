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