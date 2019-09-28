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
