# Configure a custom domain for your GitHub page

1. Take a quick scan at this [page](https://medium.com/@hossainkhan/using-custom-domain-for-github-pages-86b303d3918a) .

2. Login to your [domain](www.domain.com) services.

3. Click _Manage_

   ![](img/domain_manage.png)

4. On the left bar click on _DNS & Nameservers_ as shown below

   ![](img/dns_and_nameservers.png)

5. Modify the existing DNS record of type _**A**_ and name _**@**_ and change its content from _**66.96.xxx.xxx**_ to _**185.199.108.153**_ which is github's IP address. This should look like this

   ![](img/dns_record_1.png)

6. Add three more DNS records of type _**A**_ and name _**@**_ with content _**185.199.109.153**_, _**185.199.110.153**_, _**185.199.111.153**_ respectively.

   ![](img/dns_record_2.png)

7. Add a DNS record of type _**CNAME**_ and name _**www**_ with content _**ioanniskaragiannis.github.io.**_

   ![](img/dns_record_3.png)

8. On the root directory of the current repo go to _Settings_, scroll down and setup your custom domain as shown below. For the change to take effect it may take a few hours or even a day. Be patient. You are all set.

   ![](img/github_pages.png)

9. Confirm that you have set your custom domain successfully. 

   * On the root directory of your github repo make sure that a file with the name _CNAME_ is created with the content _ioanniskaragiannis.net_.

   * On you linux temrinal type the following:

     ```shell
     dig ioanniskaragiannis.net +noall +answer
     ```

      If everything was done properly you should see something like this

     ```console
     ; <<>> DiG 9.11.3-1ubuntu1.1-Ubuntu <<>> ioanniskaragiannis.net +noall +answer
     ;; global options: +cmd
     ioanniskaragiannis.net. 1800    IN      A       185.199.110.153
     ioanniskaragiannis.net. 1800    IN      A       185.199.108.153
     ioanniskaragiannis.net. 1800    IN      A       185.199.111.153
     ioanniskaragiannis.net. 1800    IN      A       185.199.109.153
     ```

     