DECLARE @user_name    SYSNAME
        , @login_name SYSNAME;
SELECT @user_name = 'DQ\MyUser.Name',
       @login_name = 'MyUser.Name'
SELECT 'USE ' + QUOTENAME(NAME) + ';
        CREATE USER ' + QUOTENAME(@user_name)
       + ' FOR LOGIN ' + QUOTENAME(@login_name)
       + ' WITH DEFAULT_SCHEMA=[dbo];
    EXEC sys.sp_addrolemember ''db_datareader'',''' + @user_name + ''';
    EXEC sys.sp_addrolemember ''db_denydatawriter'', ''' + @user_name + ''';
GO'
FROM   sys.databases
WHERE  database_id > 4
       AND state_desc = 'ONLINE'
