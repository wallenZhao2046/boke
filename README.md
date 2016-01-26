boke
---------

Big Data Report Description
---------------------------

[TOC]

## 在线支付分析

### 在线支付

```
create table report_mb_payment(
  id int(20) not null primary key AUTO_INCREMENT,
  report_type int(2) comment '0 按支付类型, 1 按支付金额范围paymentMoney_rage, 1 按支付类型和当物类型',
  paymentMoney_rage varchar(20) comment '支付金额区间',
  pawnMoney_rage varchar(20),
  payment_type varchar(10) comment '支付类型',
  item_category_str varchar(10) comment '当物类型',
  billCount int(10) comment '支付笔数',
  sumPaymentMoney double(10,2) comment '支付金额合计',
  sumPawnMoney double(10, 2) comment '典当金额合计'
);
```

### 在线支付用户

```
create table if not exists report_mb_pawner(
  id int(20) not null primary key AUTO_INCREMENT,
  report_type int(2) comment ' 0年龄段 pawner_age_rage, 1 性别 pawner_gender' ,
  pawner_age_rage varchar(10),
  pawner_gender varchar(10),
  payment_type varchar(10),
  item_category_str varchar(10),
  billCount int(10),
  sumPayment double(12,2),
  sumPawnmoney double(12, 2)
);
```

### 支付来源地

```
create table if not exists report_mb_location(
   id int(20) not null primary key AUTO_INCREMENT,
   report_type int(2) comment '0城市(包括直辖市的区), 1 省份' ,
   province varchar(20),
   city varchar(40),
   payment_type varchar(10),
   item_category_str varchar(10),
   billCount int(10),
   sumPayment double(12, 2),
   sumPawnmoney double(12, 2)
);
```

### 业务类型

```
create table report_mb_businessType(
  id int(20) not null primary key AUTO_INCREMENT,
  report_type int(2) comment '0业务类型',
  business_type int(2) comment '1 续当支付 2 赎当支付',
  payment_type varchar(10),
  item_category_str varchar(10),
  billCount int(10),
  sumPayment double(12,2),
  sumPawnmoney double(12, 2)
);
```
