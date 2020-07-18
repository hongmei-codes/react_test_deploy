# How to Deploy React App using GitHub Pages?

## Step 1: create a React Application
In terminal, navigate one directory up the project folder and run:
```
npx create-react-app react_test_deploy
```
Build your application and go to the next step.

## Step 2: install gh-pages
Run the following command in terminal in the project directory:
```
npm install gh-pages --save-dev
```
The ` --save-dev  ` command will add ` devDependencies ` to your package.json. It is required for deployment so, make sure you include  ` --save-dev  ` in the command.

If you want to use yarn, you can run:
```
yarn add gh-pages
```

## Step 3: create GitHub repository
Tip: https://github.com/new takes you straight to create new repository page. (You have to log in for the link to work.)

Remeber: Create an empty repository, __*don't*__ init with a README.md because it comes with the standard React app.

## Step 4: add remote link to your git
Copy the remote git URL of your new repository. In your local project directory run the git command below:
```
git remote add origin https://git.url.of.your.remote.repository/
```

## Step 5: edit package.json
Open package.json, above ` "dependencies": {...`, add the following:
```
"homepage": "https://your_github_username.github.io/your_repo_name",
```
To `  "scripts" `, add the following:
```
"predeploy": "npm run build",
"deploy": "gh-pages -d build"
```

If you want to use yarn, you can add:
```
"predeploy": "yarn build",
"deploy": "gh-pages -d build"
```

So, your `  "scripts" ` should looking like the following:
```
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  },
```

## Step 6: push your code to GitHub
To push your code, run the following in order:
```
git add .
git commit -m "your commit message"
git push -u origin master
```

## Step 7: deploy your React application
In the project directory, run the following command:
```
npm run deploy
```
If everything works correctly, you should see something like
> 'To publish this at https://your_github_username.github.io/your_repo_name, run: ...'


If you want to use yarn, you can run:
```
yarn run deploy
```

# Step 8: go to your github page
Everything is now done and you can visit your github page at 'https://your_github_username.github.io/your_repo_name'.

The github page for this demo deployment is [here](https://hongmei-codes.github.io/react_test_deploy).