**Installation**

1. Rename .env.example to .env

2. RUN `docker-compose build`

3. RUN `docker-compose up`


main application - http://localhost:8080
phpMyAdmin - http://localhost:8081
rabbitmqUI - http://localhost:15672

**Create a table**

`
CREATE TABLE videos(
id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
video_id VARCHAR(30) NOT NULL,
title VARCHAR(500) NOT NULL,
created_date TIMESTAMP
);
`


**Expectation**

1. Search Youtube videos (max of 50 at a time)

2. Save video

3. View all saved videos

4. Delete videos 

5. Can select all or deselect all videos / inverted select

6. Run receiver_1 (1 to 4) on multiple terminals

7. You should see a queued video saved message when videos are save (a basic demo of rabbitMQ)

8. The first time you view all saved videos, the system returns record from database and saves it into the cache

9. If same record is querried within 1 hr, the cached version is returned and cache expires after one hour 



