
# First Project Start chef with Download..
You can check there are so many way to download i find the way to download more easily:

# Before we download this we need the file to install file which will help to run the chef.
sudo yum install -y libxcrypt-compat

# Now Here is the link for the Chef Download :

curl -L https://omnitruck.chef.io/install.sh | sudo bash

# Now Create the New folder in the Computer

mkdir cookbooks  
# check the folder
ls 
# Go into the folder
cd cookbooks
# Generate the Cookbook
chef generate cookbook test-cookbook
# Go inside the cookbook
cd test-cookbook
# Generate the recipe 
chef generate recipe test-recipe

# Now write the code to create the file 

vi test-cookbook/recipes/test-recipe.rb

# Check the file Error in the File

chef exec ruby -c test-cookbook/recipes/test-recipe.rb

# Execute the file 

chef-client -z -o "test-cookbook::test-recipe"

# Congratulations You Done It

