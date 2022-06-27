# demo-plumber-tableau-penguins

A demo of using [plumbertableau](https://rstudio.github.io/plumbertableau/index.html) to create APIs that Tableau can consume.

- Code: <https://github.com/SamEdwardes/demo-plumber-penguins>
- API Deployment: <https://colorado.rstudio.com/rsc/demo-plumber-tableau-penguins/>
- Tableau Deployment: <https://us-west-2b.online.tableau.com/#/site/rstudio/workbooks/472632?:origin=card_share_link>

![plumber-tableau](https://user-images.githubusercontent.com/18248949/176033992-aa2633a4-8a6d-4501-8cf7-7087f18dd1fc.gif)

## API Deployment

### Git-backed

After making any code changes run the following:

```r
renv::snapshot()
rsconnect::writeManifest("app")
```

Next, push your changes to git. RStudio Connect will then automatically redeploy the app.

### Programatic

You can also deploy the app using the rsconnect api:

```r
rsconnect::deployAPI(
  api = "app",
  appFiles = c("plumber.R"),
  appTitle = "Plumber Tableau Penguins"
)
```

## Tableau Deployment

After deploying the API follow the instructions from <https://rstudio.github.io/plumbertableau/articles/tableau-developer-guide.html> to deploy in Tableau.