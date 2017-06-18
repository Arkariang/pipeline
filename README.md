

## Create docker image with the dockerfile

$MacBook-Pro-de-Isabel:setupJ isabelmartin$ pwd
/Users/isabelmartin/setupJ

$MacBook-Pro-de-Isabel:setupJ isabelmartin$ docker build -t myjenkins .

$MacBook-Pro-de-Isabel:docker run -p 8080:8080 -p 50000:50000 myjenkins

And that's it!!
