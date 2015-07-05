# alpine-nginx

Minimalist Nginx image based on Alpine linux (6 MB)

## How to use the image

1. Create a `Dockerfile` in your project

    ````
	FROM coopermaa/alpine-nginx:1.6-onbuild	
    ````    

2. Build and run the Docker image:

    ````
	$ docker build -t my-website .
	$ docker run -d my-website
    ````    

3. Then point your browser at http://localhost/.

## To view a website that hosted on GitHub: 

1. Clone your or someone else's repository:

    ````
    $ git clone --depth 1 -b gh-pages https://github.com/rogerdudler/git-guide
    $ cd git-guide
    ````    

2. Create a `Dockerfile` in the cloned repo:

    ````
    FROM coopermaa/alpine-nginx:1.6-onbuild	
    ````    

3. Build and run the Docker image:

    ````
	$ docker build -t git-guide .
	$ docker run -d git-guide
    ````

4. Then point your browser at http://localhost/ to view the git-guide offline.

