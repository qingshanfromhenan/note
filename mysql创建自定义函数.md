# note

## 1.创建函数
create function INSETINTO2 (aaaa int(11))
returns int(11)
BEGIN
declare v_length int default 0;
set v_length=aaaa;
WHILE v_length > 0 DO


DELETE from tablename where id=@id;
DELETE from table where id=@id;
SET @COUNT1=(select count(*) from lsbopen);
SET v_length =@COUNT1;
end while;

return v_length;
END;
## 2.调用函数
select INSETINTO2(1000);

## 创建函数用于汉字转拼音并取首字母
CREATE  FUNCTION `fristPinyin`(P_NAME VARCHAR(255)) RETURNS varchar(255) CHARSET utf8mb4
BEGIN
    DECLARE V_RETURN VARCHAR(255);
    SET V_RETURN = ELT(INTERVAL(CONV(HEX(left(CONVERT(P_NAME USING gbk),1)),16,10), 
        0xB0A1,0xB0C5,0xB2C1,0xB4EE,0xB6EA,0xB7A2,0xB8C1,0xB9FE,0xBBF7, 
        0xBFA6,0xC0AC,0xC2E8,0xC4C3,0xC5B6,0xC5BE,0xC6DA,0xC8BB,
        0xC8F6,0xCBFA,0xCDDA,0xCEF4,0xD1B9,0xD4D1),    
    'A','B','C','D','E','F','G','H','J','K','L','M','N','O','P','Q','R','S','T','W','X','Y','Z');
    RETURN V_RETURN;
END
;

