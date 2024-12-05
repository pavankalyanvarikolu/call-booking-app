# FROM node:17.9.0-slim
# #LABEL maintainer="DeekshithSN"
# RUN useradd userapi
# WORKDIR /app
# RUN chown userapi /app /home
# COPY . .
# RUN npm install 
# EXPOSE 1004
# # USER userapi
# # ENV MONGO_URL="mongodb+srv://pavanvarikolu:OD3QmKf8bb7AlVfZ@callbooking.x8z88.mongodb.net/?retryWrites=true&w=majority&appName=CallBooking"
# # ENV ADMIN_EMAIL="pavanvarikolu@gmail.com"
# CMD ["npm","start"]

FROM node:17.9.0-slim

WORKDIR /app

COPY . .

RUN npm install

CMD ["npm","start"]

EXPOSE 1004