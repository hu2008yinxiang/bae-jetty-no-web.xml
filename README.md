# bae-jetty-no-web.xml
configure BAE's Jetty to enable pure java configuration/annotation configuration (no web.xml)

## 说明
针对BAE使用的Jetty的start.ini配置,启用了jetty-plus.xml和jetty-annotations.xml
以下修改最新验证于2015/11/04 BAE java-jetty： open-jdk7 + **jetty-9.0.6.v20130930** + lighttpd-1.5

### 修改
```ini
# ===========================================================
# Enable additional webapp environment configurators
# -----------------------------------------------------------
OPTIONS=plus
etc/jetty-plus.xml

# ===========================================================
# Enable servlet 3.1 annotations
# -----------------------------------------------------------
OPTIONS=annotations
etc/jetty-annotations.xml
```
## Notes:
### Tomcat版本?
BAE的tomcat默认支持no-web.xml配置

### .bae/jettyconf
BAE Jetty自定义目录,该目录下的文件将会被复制到/home/admin/runtime/jettyconf

### .bae/jettyconf_bae
BAE Jetty原始配置,该目录下的文件来自未修改过的/home/admin/runtime/jettyconf
可用来进行重置或者自定义参考.
