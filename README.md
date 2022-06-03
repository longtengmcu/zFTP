# zFTP

A light weight FTP client software package, It tested success from the vsFTP in Linux. You can use zftp to download or upload files from the server. The common application is to realize the software upgrade function of the product.  
Dependent components： SAL, POSIX, DFS, TCP/IP  
Dependent the FAL package when you use the zFTP demo 

# API
/*********************************************************************************************************  
** Function name：      zFTP_login()  
** Descriptions:        ftp login server  
** input parameters：   user_name, password, server_ip  
** output parameters：  None  
** Returned value:      zftp_client or RT_NULL  
*********************************************************************************************************/  
zftp_client *zFTP_login(char *user_name, char *password, char *server_ip) 
   
  
/*********************************************************************************************************  
** Function name：      zFTP_set_callback()   
** Descriptions:        set the file download and upload callback function  
** input parameters：   ftp, dw_write, up_read, user_data  
** output parameters：  None  
** Returned value:      RT_EOK  
*********************************************************************************************************/  
int zFTP_set_callback(zftp_client *ftp, down_callback  dw_write, up_callback up_read, void *user_data) 

/*********************************************************************************************************  
** Function name：      zFTP_change_path()  
** Descriptions:        change the path of FTP server  
** input parameters：   ftp, path, path   
** output parameters：  file_size   
** Returned value:      zftp_client   
*********************************************************************************************************/  
int zFTP_change_path(zftp_client *ftp, char *path)  


/*********************************************************************************************************  
** Function name：      zFTP_upload_file()  
** Descriptions:        upload the file to FTP server  
** input parameters：   ftp, path, file_name  
** output parameters：  file_size  
** Returned value:      zftp_client  
*********************************************************************************************************/  
int zFTP_upload_file(zftp_client *ftp, char *file_name) 

/*********************************************************************************************************  
** Function name：      zFTP_get_filesize()  
** Descriptions:        get the file size from FTP server  
** input parameters：   ftp, path, file_name  
** output parameters：  file_size  
** Returned value:      zftp_client  
*********************************************************************************************************/  
int zFTP_get_filesize(zftp_client *ftp, char *file_name, rt_uint32_t *file_size)  

/*********************************************************************************************************  
** Function name：      zFTP_download_file()  
** Descriptions:        download the file from FTP server  
** input parameters：   ftp, path, file_name  
** output parameters：  file_size  
** Returned value:      zftp_client  
*********************************************************************************************************/   
int zFTP_download_file(zftp_client *ftp, char *file_name)  
   
/*********************************************************************************************************  
** Function name：      zFTP_quit()  
** Descriptions:        ftp logout and realse the zftp_client  
** input parameters：   ftp  
** output parameters：  None   
** Returned value:      RT_EOK  
*********************************************************************************************************/  
int zFTP_quit(zftp_client *ftp)  

# How to Use
See the zFTP_demo.c   use the command line: ftp file_name upload/dwload   
You must define the FTP username,ftp password,ftp server ip, file path

zFTP demo step:
1. login the ftp server by the ftp = zFTP_login(FTP_USER_NAME, FTP_PASSWORD, FTP_SVR_ADDR)  
2. set the file download callback function(file_write) and file upload callback function(file_read) by the zFTP_set_callback(ftp, file_write, file_read, RT_NULL)
3. set the seriver file path by the zFTP_change_path(ftp, FTP_SVR_PATH)
4. upload the file use the  zFTP_upload_file(ftp, filename))
5. download the file use the zFTP_download_file(ftp, filename))
6. quit from the ftp server  by the zFTP_quit(ftp)

# Author
   longteng in Beijing CHINA(中国), you can connect me sent a email to fhqlongteng@163.com   




