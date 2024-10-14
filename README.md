# Azure-VM-Tasks

**Task 1: VM Creation using azure portal**

Go to azure portal->search virtual machines->click create vm->In basics tab you have to give subscription,resiurce name,vm name, region,availability zone,image,vm size,vm username and password, inbound port -> In disks tab select os disk 127Gb, Disk type as HDD or SDD, Yo can enable delete with vm option, You can also add data disk ->In Networking tab select vnet,subnet,public ip which is used to login vm,NIC card, inbound port-> In advanced tab you can add user data to install your script automatically while creating vm -> You can also add tags-> Finally click review and create.
Now you can login Your vm using public ip, vm username and password

**Task 2  : VM Creation using azure cli**

Download azure cli from chrome and install it-> go to your command prompt in your local->type az version to check whether it is installed or not-> type az login to login->use below commands and give values.
az vm create \
  --resource-group <your-resource-group> \
  --name <your-vm-name> \
  --image <image-sku> \
  --admin-username <your-username> \
  --admin-password <your-password> \
  --size <vm-size>

  (Use chatgpt for further reference)

  **Task 3 : VM Creation using azure image** 

  Before using azure image, you should generalize your virtal machine to change OS level name of vm's.

  Go to azure portal->create one vm using azure portal-> now go to chrome and search sysprep windows installation and copy the command WINDIR/system32/sysprep/Sysprep.exe->login your vm and press windows+R and paste the copied command and enter-> Now sysprep application is installed in your vm. go to right click sysprep and run as adminstratoe. 
  Now your vm is generalized.

  Go to azure portal->go to create azure vm in portal-> click overview->click capture-> click create an image->give name,region-> click create.

  Go to your created zure image->click overviwe->click create vm->select your azure image->give size of vm,username,password,disk,vnet->click review and create

  Now yoyr new vm is created by using azure image.

  **Task 4 : VM Creation using snapshots**

  Go to azure portal->click os disk->click overview->click create snapshot->give subscription,snapshot name, select full snapshot type->click create snapshot.

  Go to your create snapshot->click create disk

  Go to your created new disk->  click create vm.(but this vm have not username and password. use your original vm username and password to login)

  **Task 5 : Connect vm vis bastion**

  Bastion is a browser based login without need of public ip.

  Go to your created vm-> click overview->click connect-> select connect via bastion

  **Task 6: Reset a passwaord in azure vm:**

  Go to azure portal-> click your created vm-> Click reset pasdswod option under help tab.
  You can reset a password for admin user. you can also create user and rest a password for him.

  **Task 7 : Azure VM Troubleshooting**

  If your vm is in hung state you can try reapply and redeploy options to trouble shoot.

  Go to azure portal-> click your created vm-> Click reapply and redeploy option under help tab.-> click reapply(now your vm is refreshed)-> if reapply is not worked click redeploy.

  **Task 8 : Host VM in different availability zones**

  Go to azure portal->click create vm->give vm name,selct region->choose availability option as availability zone->select 2 availability zones->select size of vm->give username and password->click create vm.  (2 public ip's are created in same vm)

  **Task 9: Scale set on Azure vm**

  Go to azure portal->search virtual machine scale set->click create scvale set->select subscription,Resource group->Give scale set name,region->select availability zone->choose orchestration mode as flexible or uniform-> choose security typ as standard->select manual or auto scaling ->selece instance count you want->select image,size of vm-> click review and create

  **Task 10: Availability set on azure vm**

  Your vm is running on physical servers in azure datacenter. If any failure occurs on physical servers, you can use availability set.

  Go to your azure portal->search availability set->click create->give name of av set, region->choose how many fault domain and update domain you want->click review and create.

  Go to azure portal->search virtual machines->click create vm->give vm name,region->give availability option as availability set->choose az image,vm size->click review and create.

  Now go to your created av set, you can see your vm is running in fault domain and update domain.

  **Task 11 : Azure vm upgarde or downgrade**

  Go to azure portal->go to your created vm->click size under availability+scale option->choose your vm size which you want to upfrade or downgrade.

  **Task 12 :  Azure Disk extension** 

  Go to azure portal->search virtual machines->select one vm->click disk under setting->select os disk->click size and performance under settings->change size ->click save

  Now login your vm and go to disk management. right click your os disk and select extend volume.

  Note: while extending os disk, vm should be in stopped state.
        Os disk cannot be downgraded.

    Go to azure portal->search virtual machines->select one vm->click disk under setting->select data disk disk->click size and performance under settings->change size ->click save

     Now login your vm and go to disk management. right click your data disk and select extend volume.

  Note: while extending data disk, vm can be in running or  stopped state.

  

  
