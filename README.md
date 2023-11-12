# Dockerfile
書いたDockerfileをまとめておく場所

## 豆知識
- php+apacheイメージの起動方法： `docker run --rm -it -p 80:80 php:8.1-apache`
- apacheの再起動方法：`service apache2 restart`
- 以下のエラーが出たら`apt install libc-client-dev`で直ると思う
  - `configure: error: utf8_mime2text() has new signature, but U8T_CANONICAL is missing. This should not happen. Check config.log for additional information.`
