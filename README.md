Below is a simple, step-by-step guide to create a Docker image from that React GitHub repo and push it to Docker Hub.



Prerequisites
Make sure you have:
✅ Git installed
✅ Docker installed
✅ A Docker Hub account

Step 1: Clone the GitHub repository
# git clone https://github.com/MdRasel0/sample-react-counter.git
# cd sample-react-counter

Step 2: Create a Dockerfile
Inside the project root directory, create a file named Dockerfile

$ sudo nano Dockerfile

# Step 1: Build the React app
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Step 2: Serve the app using Nginx
FROM nginx:alpine

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]


Step 3: Build the Docker image
Run this command from the project directory:
$ docker build -t sample-react-counter .
$ docker images


Step 4: Tag the image for Docker Hub
Replace your_dockerhub_username with your real Docker Hub username.

$ sudo docker tag sample-react-counter:latest nawshad298/reactapp:latest

Step 5: Login to Docker Hub
$ docker login

Step 6:
Login Docker Hub > my hub > Create repository > Repository name > “simplereact” > Short description > “it’s a simple react app repo for demo” > public > create 

Step 7:Push the image to Docker Hub
$ sudo docker push nawshad298/reactapp:latest


Pull and Build:
Step 1 Remove local image to test properly
$ sudo docker rmi <image name>

Step 2️ Pull the image from Docker Hub
$ sudo docker pull nawshad298/reactapp:latest

Step 3️ Run the container
sudo docker run -d --name reactapp-container -p 80:8000 nawshad298/reactapp:latest

Step 4️ Verify container is running
$ sudo docker ps
