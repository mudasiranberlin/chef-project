# Chef Installation and First Project Setup

This guide walks you through installing Chef and creating your first Chef cookbook and recipe.

## Prerequisites

Before installing Chef, install the required compatibility package:

```bash
sudo yum install -y libxcrypt-compat
```

## Install Chef

Run the following command to download and install Chef:

```bash
curl -L https://omnitruck.chef.io/install.sh | sudo bash
```

Verify the installation:

```bash
chef --version
```

---

## Create Your First Chef Project

### 1. Create a Working Directory

```bash
mkdir cookbooks
```

Verify that the directory was created:

```bash
ls
```

Navigate into the directory:

```bash
cd cookbooks
```

### 2. Generate a New Cookbook

Create a cookbook named `test-cookbook`:

```bash
chef generate cookbook test-cookbook
```

Move into the cookbook directory:

```bash
cd test-cookbook
```

### 3. Generate a Recipe

Create a recipe named `test-recipe`:

```bash
chef generate recipe test-recipe
```

---

## Edit the Recipe

Open the recipe file:

```bash
vi recipes/test-recipe.rb
```

Add your Chef code and save the file.

---

## Validate the Recipe

Check the recipe for Ruby syntax errors:

```bash
chef exec ruby -c recipes/test-recipe.rb
```

If the output shows:

```text
Syntax OK
```

your recipe is ready to run.

---

## Execute the Recipe

Run the recipe in local mode:

```bash
chef-client -z -o "test-cookbook::test-recipe"
```

---

## Project Structure

```text
cookbooks/
└── test-cookbook/
    ├── recipes/
    │   └── test-recipe.rb
    ├── metadata.rb
    └── README.md
```

---

## Congratulations! 🎉

You have successfully:

* Installed Chef
* Created your first cookbook
* Generated a recipe
* Validated the recipe
* Executed the recipe locally

You are now ready to start automating infrastructure with Chef.
