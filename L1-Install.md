#Lesson 1 - Install

> For mac OSX(Yosemite)

- `brew update`

- `brew install mongodb`

- After that run `mongod` to boot up your database service.

- By default, the data path is set to `/data/db/`.

- So, don't remember to create the dir. `sudo mkdir -p /data/db`



## Optional

- You can store data whereever you want.

- `mongodb --dpath DIRNAME`
