# node

npm install pm2@3.2.4 -g
pm2 -v  //3.2.4 확인
pm2 start main.js
pm2 list  // watching 이 disabled 면 pm2 stop main 후 pm2 start main.js --watch 해주기!