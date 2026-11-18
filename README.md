## Notes on Command Lines

### Environment Setup 
The following command line creates the virtual environment where the project is run.
```
uv sync
```
### Project Setup 
This will create a folder under current direcotry named {project_name}. The folder container file structure that's needed for the project. 
```
dbt --project-name {project_name}
```

Create a profiles.yml under `/.dbt`, which specifies the details of making the db connection. 

```
dbt debug
```
This will check both the `dbt_project.yml` and `profiles.yml` then opens the connection.

```
dbt ls
```
This is another inspection command in addition to `dbt debug`. It prints out all different nodes and associations with macros, tests, seeds and models. Aka it lists everything in the repo.

```
dbt seed
```
This loads the files in the `/seeds` folder and turn them into tables populating the database.

```
dbt run
```
This compiles each model to SQL (tables/ views) then runs it.

📍 Note that the model refers to `.sql` files that describe a table/ view. By default, a model generates a view. 

``` 
dbt compile 
```
This compiles each model to SQL but does NOT run anything.