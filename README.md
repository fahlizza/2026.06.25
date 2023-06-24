# 2026.06.25
code
import requests
from lxml import html
url = 'https://movie.douban.com/'#需要爬数据的网址
header = {
    "User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
} #爬虫伪装
page = requests.Session().get(url, headers=header)
tree = html.fromstring(page.text)
result = tree.xpath('//td[@class="title"]//a/text()')#获取需要的数据
print(result)
