---
id: playwright_installation
aliases:
  - Playwright_installation
tags: []
---

# Playwright_installation


```bash
mkdir ~/playwright_libs
cd ~/playwright_libs

ln -s /usr/lib/libicudata.so.76.1 libicudata.so.66
ln -s /usr/lib/libicui18n.so.76.1 libicui18n.so.66
ln -s /usr/lib/libicuuc.so.76.1 libicuuc.so.66
ln -s /usr/lib/libffi.so.8.2.0 libffi.so.7
ln -s /usr/lib/libwebp.so.7.2.0 libwebp.so.6
ln -s /usr/lib/libxml2.so libxml2.so.2

export LD_LIBRARY_PATH=~/playwright_libs

```
