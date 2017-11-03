## Dryusdan/ghost

![](https://img.shields.io/badge/Ghost%20version-1.16.0-blue.svg)



#### What is this? What features?
- A **simple** Ghost CMS build made for production.
- Based on Alpine Linux so it's lightweight!
- Bundled with latest node.js available (version check is disabled).
- Offers Isso integration.

#### Build-time variables
- **VERSION** : version of Ghost.

#### Environment variables
- **GID** : ghost user id *(default : 991)*
- **UID** : ghost group id *(default : 991)*
- **ADDRESS** : your domain (with *http(s)://*) *(default : https://my-ghost-blog.com)*
- **ENABLE_ISSO** : enables Isso support if set to *True* *(default : False)*
- **ISSO_HOST**, **ISSO_AVATAR**, **ISSO_VOTE** : Isso settings (*True* or *False*)

#### Volumes
- **/ghost/content** : contents of your blog

### Ports
- **2368** [(reverse proxy!)](https://github.com/hardware/mailserver/wiki/Reverse-proxy-configuration)

### How to configure?
Everything you need is in `/ghost/content/ghost.conf` (also mounted on your host...).

### docker-compose.yml sample

```
ghost-myblog:
  image: dryusdan/ghost
  container_name: ghost-myblog
  environment:
    - UID=8100
    - GID=8100
    - ADDRESS=https://myblog.com
  volumes:
    - /mnt/docker/myblog:/ghost/content
```
