# CST8915 Lab 5: Docker

**Name:** Dhruvansh Zala

**Student ID:** 041214130

**Course:** CST8915 Full-stack Cloud-native Development

**Semester:** Fall 2026

## Demo Video

🎥 [Watch my demo](https://youtu.be/T8MMyaBdbWY)

## What I did

In this lab I put the Pet Store app into Docker containers. I made a Dockerfile for each service, ran everything together with Docker Compose on my Azure VM, and pushed the images to Docker Hub. At the end, I ran the app again using only my Docker Hub images.

## My forks

- Order Service: https://github.com/Dzala02/order-service-L4
- Product Service (Python): https://github.com/Dzala02/product-service-python-L4
- Store Front: https://github.com/Dzala02/store-front-L4

## My Docker Hub images

- https://hub.docker.com/r/dzala0210/order-service
- https://hub.docker.com/r/dzala0210/product-service
- https://hub.docker.com/r/dzala0210/store-front

## Details

- I used the **Python** version of the Product Service.
- The Store Front image was built with my VM's IP, **4.223.161.122**, as the API host. It calls the Order Service on port 3000 and the Product Service on port 3030.

## How I tested it

- The products loaded in the store.
- I placed an order for 2 Dog Food ($39.98).
- I checked RabbitMQ, and the number of messages in `order_queue` went up, so the order was saved.

## What I learned

- After installing Docker, I had to run `newgrp docker` before Docker commands worked without `sudo`.
- At first I forgot to switch to the Docker Hub version of the compose file, so the pull failed. Once I used the right file with my username, it worked.
- The Store Front saves the API address when the image is built, so the image only works with the VM IP it was built for.
- My first Docker login failed because the token didn't paste right. It worked the second time.
