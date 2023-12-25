改自blackmatrix7的surge规则， 出于个人使用习惯，只改写了domain和domain-suffix部分，仅供参考，建议使用官方提供的远程规则：https://github.com/SagerNet/sing-geosite/tree/rule-set

使用示例：

{
"route": {
    "auto_detect_interface": true,
    "final": "proxy",
    "rules": [    
      {
        "rule_set": "geosite-cn",
        "outbound": "direct"
      },
      {
        "rule_set": "bilibili",
        "outbound": "direct"
      }
    ],
    "rule_set": [
    {
        "tag": "geosite-cn",
        "type": "remote",
        "format": "binary",
        "url": "https://raw.githubusercontent.com/SagerNet/sing-geosite/rule-set/geosite-cn.srs",
        "download_detour": "proxy"
      },
      {
        "tag": "bilibili",
        "type": "remote",
        "format": "source",
        "url": "https://raw.githubusercontent.com/shangguanhongxin/for-sing-box-and-surge/master/sing-box/BiliBili/BiliBili.json",
        "download_detour": "proxy"
      }
    ]
  },
