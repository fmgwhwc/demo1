USE dssp_profile;
drop table if exists vhl_type;

/*==============================================================*/
/* Table: vhl_type                                              */
/*==============================================================*/
create table vhl_type
(
   id                   varchar(50) not null,
   descript             varchar(50) comment '车型名称',
   vhl_brand_id         varchar(50) comment '品牌代码',
   vhl_series_id        int comment '车系代码',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);


drop table if exists "vhl_profile_m  车辆信息表";

/*==============================================================*/
/* Table: "vhl_profile_m  车辆信息表"                                */
/*==============================================================*/
create table "vhl_profile_m  车辆信息表"
(
   id                   varchar(50) not null comment 'id',
   customer_id          varchar(50) comment '车主编码',
   dopt_code            varchar(50) comment '发动机号',
   vhl_lisence          varchar(50) comment '车牌号',
   color                varchar(50) comment '颜色',
   remark               varchar(200) comment '备注',
   vhl_brand_id         varchar(50) comment '品牌代码',
   vhl_series_id        varchar(50) comment '车系代码',
   vhl_type_id          varchar(50) comment '车型代码',
   vhl_color_id         varchar(50) comment '颜色代码',
   vhl_status           varchar(2) comment '车辆状态',
   vhl_user_id          varchar(50) comment '车辆使用人代码',
   insurance_id         varchar(50) comment '保险公司代码',
   dealer_id            varchar(50) comment '经销商代码',
   istest               varchar(2) comment '车辆类型',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后修改时间',
   user_id              varchar(50) comment '操作人',
   area_id              varchar(50) comment '车辆所需区域',
   service_level_id     varchar(50) comment '服务等级',
   due_date             date comment '保险到期日',
   receive_date         date comment '收车日期',
   receive_cheeck_date  date comment '收车登记时间',
   insurance_phone      varchar(50) comment '保险客服电话',
   purchase_date        date comment '销售时间',
   primary key (id)
);

alter table "vhl_profile_m  车辆信息表" comment '车辆信息';



drop table if exists customer_profile;

/*==============================================================*/
/* Table: customer_profile                                      */
/*==============================================================*/
create table customer_profile
(
   id                   varchar(50) not null comment '用户id',
   descript             varchar(50) comment '用户名称',
   customer_type        varchar(2) comment '用户类型',
   credentials          varchar(2) comment '证件类型',
   credentials_num      varchar(50) comment '证件号码',
   vip_property         varchar(50) comment 'vip属性',
   pin                  varchar(50) comment 'pin密码',
   sex                  varchar(2) comment '性别',
   mary                 varchar(2) comment '婚否',
   birthday             date comment '出生日期',
   mobile_phone         varchar(50) comment '移动电话',
   phone                varchar(50) comment '座机',
   qq                   varchar(50) comment 'qq',
   min_message          varchar(50) comment '微信',
   emall                varchar(50) comment '邮箱',
   advertisement        varchar(2) comment '1接受2不接受',
   province_id          varchar(50) comment '省id',
   city_id              varchar(50) comment '市id',
   county_id            varchar(50) comment '区id',
   address              varchar(50) comment '地址',
   zip                  varchar(50) comment '邮编',
   hobby                varchar(300) comment '爱好',
   remark               varchar(300) comment '备注',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '修改时间',
   user_id              varchar(50) comment '操作人id',
   syn_num              int comment '同步次数',
   vhl_user_code        varchar(50) comment '使用人编号',
   vhl_language_code    varchar(50) comment '车机默认语言',
   customer_group       varchar(50) comment '客户分组',
   insurance_id         varchar(50) comment '保险公司id',
   insurance_name       varchar(200) comment '保险公司名称',
   vip_preferences      varchar(50) comment 'vip偏好',
   question_one         varchar(50) comment '问题1',
   answer_one           varchar(50) comment '答案1',
   question_two         varchar(50) comment '问题2',
   answer_two           varchar(50) comment '答案2',
   contact              varchar(50) comment '紧急联系人',
   contact_phone        varchar(50) comment '紧急联系人电话',
   vhl_mobile_phone     varchar(50) comment '车载主叫号',
   primary key (id)
);

alter table customer_profile comment '车主信息管理';



drop table if exists contract_profle;

/*==============================================================*/
/* Table: contract_profle                                       */
/*==============================================================*/
create table contract_profle
(
   id                   varchar(50) not null comment '合同id',
   contract_code        varchar(50) comment '合同编码',
   vin                  varchar(2) comment '车架号',
   contract_begin_time  date comment '合同开始时间',
   contract_end_time    date comment '合同结束时间',
   contract_money       decimal comment '支付金额',
   pay_mode             varchar(2) comment '支付方式',
   pay_date             date comment '支付日期',
   contract_type        varchar(2) comment '合同类型',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   user_id              varchar(50) comment '操作人id',
   syn_num              varchar(50) comment '同步次数',
   contract_url         varchar(50) comment '合同附件地址',
   file_name            varchar(50) comment '合同附件文件名',
   contract_status      varchar(50) comment '记录合同状态',
   issame               varchar(50) comment '车主是否为使用人',
   data_source          varchar(50) comment '数据来源',
   dms_id               varchar(50) comment 'dms同步数据合同id',
   contract_expire_time date comment '合同过期时间',
   contract_num         varchar(50) comment '合同编号',
   rule_id              varchar(50) comment '保养规则',
   bill_url             varchar(200) comment '发票地址',
   bill_name            varchar(500) comment '发票文件名',
   remind               varchar(2) comment '0提醒1已提醒',
   discnt_status        varchar(2) comment '是否完成套餐切换',
   release_tag          varchar(2) comment '是否解除',
   enroll_status        varchar(2) comment '1成功2失败3进行中',
   primary key (id)
);

alter table contract_profle comment '合同信息管理';




drop table if exists vhl_sale;

/*==============================================================*/
/* Table: vhl_sale                                              */
/*==============================================================*/
create table vhl_sale
(
   vin                  varchar(50) not null comment '车架号',
   customer_id          varchar(50) comment '车主代码',
   customer_name        varchar(2) comment '车主名称',
   customer_credentials varchar(20) comment '证件类型',
   customer_credentials_num varchar(2) comment '证件号码',
   customer_sex         varchar(50) comment '性别',
   customer_mobile_phone varchar(50) comment '移动电话',
   customer_h_phone     date comment '家庭电话',
   customer_email       varchar(50) comment '邮箱',
   vhl_color            varchar(50) comment '颜色代码',
   vhl_licence          varchar(200) comment '车牌号',
   remark               varchar(50) comment '备注',
   vhl_status           varchar(3000) comment '车辆状态',
   service_level_id     varchar(50) comment '服务等级',
   insruance_company    varchar(50) comment '保险公司名称',
   insurance_num        varchar(50) comment '保单号',
   due_date             date comment '保险到期日',
   sale_date            date comment '销售时间',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (vin)
);

alter table vhl_sale comment '车辆销售信息';




drop table if exists vhl_profile;

/*==============================================================*/
/* Table: vhl_profile                                           */
/*==============================================================*/
create table vhl_profile
(
   vin                  varchar(50) not null comment '车架号',
   vhl_color_id         varchar(50) comment '颜色代码',
   remark               varchar(200) comment '备注',
   vhl_brand_id         varchar(50) comment '品牌代码',
   vhl_series_id        varchar(50) comment '车系代码',
   vhl_type_id          varchar(50) comment '车型代码',
   vhl_config_id        varchar(50) comment '配置代码',
   vhl_status           date comment '车辆状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   vhl_window           varchar(50) comment '物料代码',
   primary key (vin)
);

alter table vhl_profile comment '车辆信息(经销商提供初始数据)';





drop table if exists dealer_profile;

/*==============================================================*/
/* Table: dealer_profile                                        */
/*==============================================================*/
create table dealer_profile
(
   id                   varchar(50) not null comment '经销商编码',
   descript             varchar(50) comment '名称',
   dealer_type          varchar(2) comment '经销商类型',
   area_id              varchar(20) comment '大区编码',
   status               varchar(2) comment '经销商状态',
   province_id          varchar(50) comment '省id',
   city_id              varchar(50) comment '市id',
   open_time            date comment '建立时间',
   fax                  varchar(50) comment '传真',
   email                varchar(50) comment '邮箱',
   address              varchar(200) comment '地址',
   phone                varchar(50) comment '电话',
   remark               varchar(3000) comment '备注',
   primary key (id)
);

alter table dealer_profile comment '经销商信息';


drop table if exists insurance;

/*==============================================================*/
/* Table: insurance                                             */
/*==============================================================*/
create table insurance
(
   id                   varchar(50) not null comment '城市id',
   descript             varchar(50) comment '省id',
   address              varchar(100) comment '地址',
   zip                  varchar(20) comment '邮编',
   phone                varchar(50) comment '电话',
   fax                  varchar(50) comment '传真',
   remark               varchar(200) comment '备注',
   record_statuss       varchar(2) comment '记录状态',
   primary key (id)
);

alter table insurance comment '保险信息';

drop table if exists area;

/*==============================================================*/
/* Table: area                                                  */
/*==============================================================*/
create table area
(
   id                   varchar(50) not null comment '区域id',
   descript             varchar(50) comment '名称',
   record_status        varchar(2) comment '记录状态',
   primary key (id)
);

alter table area comment '区域信息';


drop table if exists country;

/*==============================================================*/
/* Table: country                                               */
/*==============================================================*/
create table country
(
   id                   varchar(50) not null comment '区县镇id',
   city_id              varchar(50) comment '市id',
   descript             varchar(50) comment '名称',
   record_status        varchar(2) comment '记录状态',
   primary key (id)
);

alter table country comment '城镇信息  ';

drop table if exists city;

/*==============================================================*/
/* Table: city                                                  */
/*==============================================================*/
create table city
(
   id                   varchar(50) not null comment '城市id',
   province_id          varchar(20) comment '省id',
   descript             varchar(50) comment '名称',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);

alter table city comment '城市信息';


drop table if exists province;

/*==============================================================*/
/* Table: province                                              */
/*==============================================================*/
create table province
(
   id                   varchar(50) not null comment '省id',
   descript             varchar(50) comment '名称',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);

alter table province comment '省份信息';

drop table if exists vhl_color;

/*==============================================================*/
/* Table: vhl_color                                             */
/*==============================================================*/
create table vhl_color
(
   id                   varchar(50) not null,
   descript             varchar(50) comment '车型名称',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);

alter table vhl_color comment '车辆颜色';



drop table if exists vhl_series;

/*==============================================================*/
/* Table: vhl_series                                            */
/*==============================================================*/
create table vhl_series
(
   id                   varchar(50) not null comment '车系代码',
   descript             varchar(50) comment '车型名称',
   vhl_brand_id         varchar(50) comment '品牌代码',
   series               int comment '是否进口车',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);

alter table vhl_series comment '车系信息';


drop table if exists vhl_brand;

/*==============================================================*/
/* Table: vhl_brand                                             */
/*==============================================================*/
create table vhl_brand
(
   brand_id             varchar(30) not null comment '品牌代码',
   brand_descript       varchar(30) comment '品牌名称',
   record_status        varchar(30) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date not null comment '最后更新时间',
   primary key (brand_id)
);

alter table vhl_brand comment '车辆品牌';


drop table if exists vhl_type;

/*==============================================================*/
/* Table: vhl_type                                              */
/*==============================================================*/
create table vhl_type
(
   id                   varchar(50) not null,
   descript             varchar(50) comment '车型名称',
   vhl_brand_id         varchar(50) comment '品牌代码',
   vhl_series_id        int comment '车系代码',
   record_status        varchar(2) comment '记录状态',
   create_time          date comment '创建时间',
   update_time          date comment '最后更新时间',
   primary key (id)
);

alter table vhl_type comment '车型信息';


