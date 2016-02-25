# wintersmith-practice
Practiced wercker deployment of Wintersmith builds

#Takeaways

 - Wintersmith gives a template from which you can easily make a blog with ```.md``` files.
 - ```wintersmith preview``` from ```master branch``` to see full site pre-build.
 - The wercker deploy at ```gh-pages``` works by running ```wintersmith build``` and pushing the ```/build``` directory (Which contains the static HTML and associated CSS) to the ```gh-pages``` branch
 - wercker depends on creating and linking an 'app' on their site to a repo such as this one. Whenever ```master``` branch updates, wercker will run the ```wercker.yml``` file, much like a Grunt or Gulp process
    - .yml files cannot have tabs.
    - wercker 'steps' are like npm modules in which you have to define one that either exists in marketplace or author your own.
    
# CONS
 - wercker build messes up with pathing for CSS files, etc. searches vtange.github.io/main.css instead of vtange.github.io/repo-name/main.css
 - Uses templates to generate static sites - cannot be used really for unique sites. Might as well do it via Express.
