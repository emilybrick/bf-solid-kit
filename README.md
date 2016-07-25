# bf-solid-kit

A repo designed for easy to set-up Buzzfeed demos, pre-baked with Solid and SCSS

## Instructions for setup and development

*Steps 1-6 are for local development, step 7 is for deploying to your GH pages domain*

1. Fork repo into your /sites folder (or wherever makes sense in your setup)

2. Cd into the repo in your terminal

3. Checkout the gh-pages branch: `git checkout gh-pages`

4. In the terminal, run: `bundle install`. If this doesn’t work, follow the instructions below. 

    1. Run: `gem install bundler`

    2. Run: `bundle install`

    3. If that  works, skip to step 5. If it doesn’t work, go to step 4iv (below).

    4. Install Ruby through Homebrew

        1. Run: `brew` 

            * If it says, "command not found", go to [http://brew.sh/](http://brew.sh/) and follow the instructions, then go to the next step.

        2.  Run: `brew install ruby`

            * If it says "/usr/local/bin is not writable", run: `sudo chown -R `whoami`:admin /usr/local/bin`

            * If it says "/usr/local/share is not writable", run: `sudo chown -R `whoami`:admin /usr/local/share`

        3. Install bundler

            * Run: `gem install bundler`

            * Run: `bundle install`



5. Run: `npm start` to start the server (this needs to continually run, so open another tab for branching/pushing/etc). This command is actually an alias for "bundle exec jekyll serve --baseurl=''".

6. Go to [http://127.0.0.1:4000/](http://127.0.0.1:4000/) in your browser to see the site in action (see step 3 in the FAQ’s if this doesn’t work).

7. To deploy to your GH pages domain - open *config.yml*
  * Rename line 15 to whatever you named the folder when you cloned it.
  * Rename line 16 to the name of your github pages domain. 
  * Rename line 9 to your site’s title. 
  * Restart the server ( `cntrl +c`  in the terminal, and then `npm start`)
        

## FAQ’s (but mostly just f’s)

1. **Solid is included as a node module** inside your site folder, and is **not automatically updated.** To update to the latest version of Solid, you’ll need to run `npm update` before running `npm start`

2. **Create new files for custom scss** inside of the */_sass folder*. Each new scss partial created will need to be imported in */css/main.scss* (see */css/main.scss* for an import example)*.* 

3. **Your local IP** should surface in the terminal when you run  `npm start`. https://www.dropbox.com/s/4obbvsbpou35x6x/Screenshot%202016-07-02%2018.33.30.png?dl=0

4. **Work in the root directory,** not in the *_site* folder. The *_site* folder is your compiled site markup Anything you (accidentally) write in here will get overwritten when the site is compiled (aka the next time you cmd + s).

5. **Site structure:**
    * The IP will hit index.html in the **root folder**. I don’t suggest working on prototypes directly in the root folder, but rather creating folders with their own respective *index.htm*l in them. Keep the file structure easy to understand and scale! See */demo-1/index.html *for an example.
    * Reusable components, such as headers and footers, go in the *_includes* folder *(/_includes)*. Reusable layouts, such as "default", go in the *_layouts folder* *(/_layout).* 
    * You can put as many includes in your template files as you want, however each page can only have one layout.
    * The layout is determined at the top of each template, while the includes live in the template’s markup semantically. Reference* /demo-1/index.html* as an example. 

## Installing multiple BF-Solid-Kit repositories

Your first repo can be forked directly from the original BF-solid-kit. You can organize your prototype projects in a couple different ways. If you choose to have multiple prototypes inside of one repo, make sure to organize your prototypes and their respective SCSS files by folder names that make sense.
https://www.dropbox.com/s/m9ujr1yba7uv3vz/Screenshot%202016-07-25%2016.51.53.png?dl=0

If you choose to have individual repositories for each prototype, you'll need to add an upstream remote to your originally forked repo. To do this, follow these instructions step by step: https://kroltech.com/2014/01/01/quick-tip-how-to-fork-your-own-repo-in-github/


## More Information

On Jekyll and Github Pages: [https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)

On Github Pages: [https://help.github.com/categories/github-pages-basics/](https://help.github.com/categories/github-pages-basics/)

