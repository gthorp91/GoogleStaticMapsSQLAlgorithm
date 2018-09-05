ALTER FUNCTION "DBA"."IntegerToBinary"
(
    @Input INT
)
RETURNS VARCHAR(1000)
AS
BEGIN
 DECLARE @Output VARCHAR(32)

 WHILE @Input >= 1
 BEGIN
 SELECT @Output = CAST(@Input % 2 AS VARCHAR) + @Output, @Input = @Input / 2
 END

 IF(32 > LEN(@Output))
 BEGIN
 SELECT @Output = REPLICATE('0', 32 - LEN(@Output)) + @Output
 END

 RETURN @Output
END
