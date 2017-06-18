

## Create docker image with the dockerfile

isabelmartin$ pwd
/Users/isabelmartin/setupJ

isabelmartin$ docker build -t myjenkins .

isabelmartin$ docker run -p 8080:8080 -p 50000:50000 myjenkins

And that's it!!
