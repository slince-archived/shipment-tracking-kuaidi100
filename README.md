# 快递100物流信息查询

[![Build Status](https://img.shields.io/travis/slince/shipment-tracking-kuaidi100/master.svg?style=flat-square)](https://travis-ci.org/slince/shipment-tracking-kuaidi100)
[![Coverage Status](https://img.shields.io/codecov/c/github/slince/shipment-tracking-kuaidi100.svg?style=flat-square)](https://codecov.io/github/slince/shipment-tracking-kuaidi100)
[![Latest Stable Version](https://img.shields.io/packagist/v/slince/shipment-tracking-kuaidi100.svg?style=flat-square&label=stable)](https://packagist.org/packages/slince/shipment-tracking-kuaidi100)
[![Scrutinizer](https://img.shields.io/scrutinizer/g/slince/shipment-tracking-kuaidi100.svg?style=flat-square)](https://scrutinizer-ci.com/g/slince/shipment-tracking-kuaidi100/?branch=master)

快递100物流信息查询库

## Installation

Install via composer

```bash
$ composer require slince/shipment-tracking-kuaidi100
```
## Basic Usage


```php

$tracker = new Slince\ShipmentTracking\KuaiDi100\KuaiDi100Tracker(APPKEY, 'shunfeng'); //承运商名称并不是标准的承运商代码，实际承运商代码请到kuaidi100.com查看

try {
   $shipment = $tracker->track('CNAQV100168101');
   
   if ($shipment->isDelivered()) {
       echo "Delivered";
   }
   print_r($shipment->getEvents());  //print the shipment events
   
} catch (Slince\ShipmentTracking\Exception\TrackException $exception) {
    exit('Track error: ' . $exception->getMessage());
}

```
快递100的key需要自行申请，免费版的key在查询申通顺丰之类的单号时会受限，需要企业版才可以；附上快递100[文档](https://www.kuaidi100.com/openapi/api_post.shtml)

## License
 
The MIT license. See [MIT](https://opensource.org/licenses/MIT)

