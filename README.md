# devsecops2

### Launch a workflow when the code is updated

The script is there: https://github.com/charroux/devsecops2/blob/main/.github/workflows/actions.yml

Update your project with such a script and push this code to Github.

Then create a new branch on your local machine:
```
git branch newcarservice
```
Move to the new branch:
```
git checkout newcarservice
```
Update the code and commit changes:
```
git commit -a -m "newcarservice"
```
Move to the main branch:
```
git checkout main
```
Push the changes to GitHub:
```
git push -u origin newcarservice
```
Create a Pull request on GitHub and follow the workflow.

Merge the branch on Github is everything is OK.

Then pull the new main version:

```
git checkout main
```
```
git pull origin main
```

If necessary delete the branch:

```
git branch -D newcarservice
```
```
git push origin --delete newcarservice
```

### Docker

Create a Dockerfile in the code folder: https://github.com/charroux/devsecops2/blob/main/Dockerfile

Take care at Java version and also the name of the jar file (obtained with gradlew build).

Build a Docker image:
```
docker build -t devsecops .      
```
Run the container:
```
docker run -p 4000:8080 devsecops    
```
Then check in your browser:
```
http://localhost:4000/cars/AA11BB
```

### Publish the Docker image to the Docker Hub

Tager l'image :
```
docker tag 4da2332370c7 votreIdDocherHub/devsecops:1
```
où le numéro est l'identifiant de l'image donné par docker images, et 1 est un numéro de version

Se connecter au Docker Hub :
```
docker login
```

Publier l'image :
```
docker push votreIdDocherHub/devsecops:1      
```


