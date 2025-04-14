# Understanding Microfrontends Course

## Below steps to consider
1) Go to each folder and install the packages
2) Add the appropriate configurations in the webpack
3) Have a common config file along with dev and prod webpack config file
4) Use the merge method from webpack to merge the configurations of two different webpack files
5) Use the HtmlWebpackPlugin to insert all the .js in the .html file and ModuleFederationPlugin to setup details about microfront ends.
6) Take care of shared dependencies

## Deployment 
- To deploy each microfrontend independently (including the container)
- Location of child app remoteEntry.js files must be known at build time!
- Many front-end deployment solutions assume you're deploying a single project - we need something that can handle multiple different ones
- Probably need a CI/CD pipeline of some sort
- At present, the remoteEntrly.js file name is fixed! Need to think about caching issues

## Deployment Solution
- Use CI/CD pipelines in Github to perform prod build
- Whenever code is pshed into the main branch and the commit contains a change in the "container" folder
- Execute commands in a virual machine hosted by Github (Using Github Actions)
1) Change into container folder
2) Install dependencies
3) Create a production build using webpack
4) Upload the result to AWS S3
- Same will be applicable to other folders for other MFE


