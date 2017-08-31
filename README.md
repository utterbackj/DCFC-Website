# DCFC-Website

*How to update the site, step by step with no prior web development experience assumed*

## Step 1 - Downloads)
- Download Github Desktop, or just Git if you prefer command line to a GUI
- Go to https://nodejs.org/en/ and download that
- Go to https://atom.io/ and download that. If you have another text editor you like better, feel free to use it instead, but atom has css and javascript integrations that are pretty nice to have.

## Step 2 - Clone the repository)
Go to https://github.com/utterbackj/DCFC-Website and hit the button that says clone. If you're using Github Desktop, just click the button "open in desktop". Otherwise, use typical git commands (if you're using command line git, you should know these).

## Step 3 - Setup the website for local development)
- Open your favorite terminal (I prefer Git Bash or Powershell)
- Navigate to the repository folder. You can do this by using the "cd" command - for example, "cd documents/github/DCFC-Website". For a list of files and folders in the current directory, type "ls".
- Type "npm install". This installs all the project dependencies in the folder.
- Type "npm install -g bower". This installs bower on your system.
- Type "bower install". This installs all the development dependencies.

## Step 4 - Run the website locally)
- In your terminal, in the same location as before, type "npm start". This should open up a local version of the website in your browser.

## Step 5 - Make changes)
- Open Atom.
- Open the project folder (DCFC-Website)
- Edit the files in src according to what you want. More on this later.
- All changes should be reflected immediately in the browser window.

## Step 6 - Deployment)
- Type "npm build". This makes a production-ready version of the website in the "dist" folder.
- Open WinSCP (or whatever you want to use). Login to our account on the Dartmouth servers (if you don't have the account info, you need to get it - ask the captains or another appropriate authority figure) and replace everything in that folder with the contents of "dist". If you want to be more careful, I'd recommend copying the files on the server to some backup location in case you did something you'll later regret.

## Step 7 - Update the Repository)
- This step is easy to forget but very important as it allows other people to make changes to the website without getting rid of your changes.
- Open Github Desktop and under changes, type a summary/description of whatever you did.
- Hit the button that says "commit to master". You may not have enough permissions for this, please contact me if you get an error. Typically the process instead involves making pull requests or new branches, but with ~1 person developing at any given point in time I doubt this will be an issue.
- Hit the button that says "push origin". This syncs the online repository with your local one.

Repeat from step 4 - 7 whenever you want to update the site. Make sure you hit the fetch origin button if any changes have been made to the site since you last worked on it.

# Making changes:

There are certain things you'll want to keep an eye on in order to keep the site up to date.

## Homepage:

- Open the file src/pages/index.html
- Facebook: Whenever a new post is made on our facebook, click the 3 dots on the upper right of the post and click the "embed" option and then click "advanced options". Change the pixel width to 350 and then hit the "Get Code" button. Copy everything in step 3 and paste it in the section of index.html between "\<!-- Facebook - Update with latest post -->" and "\<!-- End of Facebook html, don't replace past here -->"
- Instagram: On a post, click the 3 dots on the bottom right and hit the "embed" option. Then click the button that says "copy embed code" and paste that between the instagram comments right underneath the facebook embedded post. Make sure you don't choose the same topic for both the Facebook and Instagram post (happens often when we go to competitions or someone gets an award or something), this looks bad. A nice alternative is using the most recent facebook and second most recent Instagram post (it's ok if the new instagram post was the old facebook post, as long as the same post isn't on both at the same time).
- Don't worry about the article headers, that'll update automatically when you edit the json file
- You may want to keep the intro up to date with our latest accomplishments and/or selling points to the team

## Roster:

- Update captains and officers manually by editing the src/pages/roster.html file.
- For the rest of the page, you need to update the assets/roster/roster_data.js file (and add/remove pictures to the assets/img/roster folder). Follow the same format for new entries, and when you need to update the roster for a new class year, delete all the entries until the first one is the current seniors. The json is sorted by class year (oldest to youngest) so add new entries to the bottom for freshmen or with the rest of their class for upperclassmen. If someone quits or stops showing up, just change the inactive variable to true; this makes it easy if they rejoin to just change it back and they'll be back in the roster. Make sure you spell/capitalize all categories the same way they're spelled in the rest of the entries or the filters will break.
- For images, any dimension is fine as long as it's square. Image type can be either png or jpg, just make sure you add the right file extension to the json file when typing in the file name.

## Articles:

- Articles should be done entirely in the assets/articles/article_data.js file. Key should be the next number up (doesn't really matter as long as it's unique, so if you delete an article don't worry about changing the keys for subsequent articles). The "body" field is an array of paragraphs; each paragraph should be in quotes and separated by a comma like "paragraph one", "paragraph two".
- Add articles to the top of the file; newest should be above oldest.
- If you want any additional functionality (like attaching a picture to the article) let me know and I'll implement that for you.

## Competitions:

- This is a static page, just make sure to keep it updated when competitions are announced and after we get results from each of them.

## Other pages:

- The rest of the pages are all static and don't need frequent updates, just make sure to check in like once or twice a year and update the text and images with newer info so that it doesn't get too outdated (some of them reference some pretty old stuff already, so this is something you want to do when starting to update the site).
