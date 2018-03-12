# -NodeJS-

Step 1. Prepare package 

  node-v6.11.5-linux-x86.tar.xz @ https://nodejs.org/dist/v6.11.5/
  
  pm2-2.7.1.zip @ https://github.com/Unitech/PM2/releases
  
       1. upload pm2-2.7.1 to a server with internet and npm.
       2. unzip pm2-2.7.1
       3. cd pm2-2.7.1
       4. npm install
       5. cd ..
       6. mv pm2-2.7.1 pm2
       7. zip -r pm2.zip pm2
       
   now you have both nodejs and pm2 package.
     
Step 2. Upload nodejs and pm2 packages to the server without internet.
     first install nodejs.
     
     1. tar xf node-v6.11.5-linux-x64.tar.xz 
     2. cd node-v6.11.5-linux-x64
     3. cp -r ./lib/node_modules/ /usr/local/lib/
     4. cp -r ./include/node /usr/local/include/
     5. mkdir -p /usr/local/man/man1/
     6. cp ./share/man/man1/node.1 /usr/local/man/man1/
     7. ./bin/node /usr/local/bin/
     8. ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm
     
     done.
     
     next install pm2.
     
     1. unzip pm2.zip
     2. cp -r ./pm2 /usr/local/lib/node_modules/
     3. ln -s /usr/local/lib/node_modules/pm2/bin/pm2 /usr/local/bin/pm2
     4. ln -s /usr/local/lib/node_modules/pm2/bin/pm2-dev /usr/local/bin/pm2-dev
     5. ln -s /usr/local/lib/node_modules/pm2/bin/pm2-docker /usr/local/bin/pm2-docker
     6. ln -s /usr/local/lib/node_modules/pm2/bin/pm2-runtime /usr/local/bin/pm2-runtime
     
     done.
     
 Step 3. install mongodb
     download mongodb-linux-x86_64-rhel70-3.4.10.tgz @ https://www.mongodb.com/download-center?_ga=2.48853798.1419394692.1517560806-1714444005.1505280691#production
     
     1. tar -zxvf mongodb-linux-x86_64-rhel70-3.4.10.tgz
     2. cd mongodb-linux-x86_64-rhel70-3.4.10
     3. cp ./bin/* /usr/local/bin/
     4. mkdir /data/db
     5. mongod --dbpath /data/db
     
 Step 4. install redis
     download redis-3.2.11.tar.gz @ https://redis.io/download/releases Old (3.2)
     
     1. tar -xvf redis-3.2.11.tar.gz
     2. cd redis-3.2.11.tar.gz
     3. make
     4. make install
     
