# lab009
lab009

1.9
![image](https://github.com/user-attachments/assets/adf79b7d-8e0d-4d3d-b00e-0d09258f8705)


(ไม่มีnpm :: npm install -g npm)
npm install -g pnpm
pnpm install
pnpm build
docker build -t kengchayodom/nuxt-app .

2.7
![image](https://github.com/user-attachments/assets/6e9329d5-c0eb-4d12-b065-b1136a767db2)


2.8

docker run -p 3000:3000 kengchayodom/nuxt-app
![image](https://github.com/user-attachments/assets/02ec56d2-24bf-4017-9ed5-b4c68eddcfe2)

2.9
FROM node:23-alpine AS build

WORKDIR /app

COPY package.json pnpm-lock.yaml ./

RUN npm install -g pnpm && pnpm install

COPY . .

RUN pnpm run build

FROM node:23-alpine

WORKDIR /app

COPY --from=build /app/.output /app/.output

EXPOSE 3000
# Start the application
CMD ["node", ".output/server/index.mjs"]


2.10

![image](https://github.com/user-attachments/assets/978e6ff7-8b6f-4a71-a61e-798a6e066e0f)


3

docker push kengchayodom/nuxt-movie
docker push kengchayodom/nuxt-app
![image](https://github.com/user-attachments/assets/daf8c5c9-ecd6-43d1-abfc-048404e7cf4b)

4
docker pull kengchayodom/nuxt-movie
docker run -p 3000:3000 kengchayodom/nuxt-movie
![image](https://github.com/user-attachments/assets/13910b5a-a975-4e6e-948e-50bde420d88d)


5.

npm install -g pnpm
pnpm install
pnpm build
docker build -t kengchayodom/vue3-realworld .
docker push kengchayodom/vue3-realworld

connect VM

docker pull kengchayodom/vue3-realworld
docker run -p 8080:80 kengchayodom/vue3-realworld

![image](https://github.com/user-attachments/assets/285ef527-9c21-4ddb-8b89-c34997aac65e)



