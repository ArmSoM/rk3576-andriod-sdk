# ArmSoM-SDK Release Guide  

ArmSoM provides Linux and Android SDKs for all its products. These SDKs are typically hosted on Baidu Netdisk. This guide uses the **ArmSoM-CM5IO** as an example to demonstrate how to obtain and compile the SDK firmware.  

---

## **Obtaining the SDK**  
Click the following link to access the SDK: [GitHub](https://github.com/ArmSoM/rk3576-andriod-sdk/releases/tag/rk3576_Android14RKR6)  
Download all partition archives to your PC.  

---

## **Extracting the SDK**  
Place all the partition archive files in the same directory and execute the following commands to extract them:  

```bash  
cat rk3576_android14.tar.bz2.a* | tar xj  
cd rk3576_android14  
```  

---

## **Configuring the Product SDK**  
After extracting the SDK, you can view the Git commit history.  

This SDK contains the general RK3576 code and can be used to build firmware for both **Sige5** and **CM5IO**. The firmware link mentioned above includes a patch specific to CM5IO. Apply the patch using the following command:  

```bash  
git am /path/to/your/patches/*.patch  
```  

---

## **Compiling the SDK**  
Once you have the SDK, compile it using the following steps:  

```bash  
source build/envsetup.sh  

lunch  

./build.sh -AUKup  
```  

After executing the `lunch` command, select the **userdebug version** for CM5IO.  

---

## **Compilation Issues**  
If you encounter issues during the compilation process, you can seek help by posting questions or browsing known issues on the [forum](https://forum.armsom.org/tag/sdk).  

For Linux SDK operations, refer to the blog published by ArmSoM:  
[https://blog.csdn.net/nb124667390/category_12589795.html](https://blog.csdn.net/nb124667390/category_12589795.html)  
