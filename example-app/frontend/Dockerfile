FROM ubuntu:24.04

WORKDIR /app/frontend
COPY 1_12 .

EXPOSE 5001
ENV GIN_MODE=release
ENV REACT_APP_BACKEND_URL=http://localhost:8080/

RUN apt update && apt install -y curl

# Node
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash && apt install -y nodejs
RUN node -v && npm -v && npm install

# Start production
RUN npm run build && npm install -g serve

CMD ["serve", "-s", "-l", "5001", "build"]

