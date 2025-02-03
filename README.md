<p align="center">

  ![image](https://github.com/user-attachments/assets/12fc89ca-b2a6-49aa-93f3-f0b74e01147c)

</p>
<h1>Building an Intuition for DNS</h1>
<h2>Objectives</h2>
The objective is to build a practical understanding of DNS records, including A-records, CNAME records, and local DNS caching. The exercises focus on creating, modifying, and troubleshooting DNS entries, and understanding the role of DNS caching.<br />


   <h2>1. A-Record Exercise</h2>

  <h4>Steps:</h4>

1)  Log into DC-1 (Domain Controller) and Client-1 as domain admin.

2)  On Client-1, attempt to ping “mainframe”. The request will fail due to the absence of a DNS record.

3)  Use the nslookup command on Client-1 to verify the lack of an existing DNS record for “mainframe”.

4)  On DC-1, create a DNS A-record for “mainframe” and point it to DC-1's private IP address.

5)  Return to Client-1 and try to ping “mainframe” again. This time, the ping should succeed, indicating the DNS record was successfully added.

    <h3>Key Learning:</h3>
<h4>You learn how to create and assign an A-record (Address record) to a hostname and map it to an IP address within a DNS server.</h4>

 
![image](https://github.com/user-attachments/assets/4cb242a6-48d0-4e9f-a69e-d3998f5c8064)
   <h2>2. Local DNS Cache Exercise</h2>

  <h4>Steps:</h4>

1)  On DC-1, change the mainframe’s DNS record to point to 8.8.8.8 (Google’s DNS).

2)  Go back to Client-1 and attempt to ping “mainframe” again. You’ll notice that the request still resolves to the old address.

3)  On Client-1, use the ipconfig /displaydns command to inspect the local DNS cache.

4)  Flush the DNS cache on Client-1 by running ipconfig /flushdns in the command prompt.

5)  Run ipconfig /displaydns again, and you’ll see the DNS cache is now empty.

6)  Attempt to ping mainframe once more. The new DNS record (pointing to 8.8.8.8) should now be resolved.

    <h3>Key Learning:</h3>
<h4>You gain an understanding of DNS caching and how to manage it using the ipconfig command. Flushing the cache helps you clear outdated or incorrect DNS entries.</h4>


![image](https://github.com/user-attachments/assets/c28c776a-7401-4d9a-9204-9f4e44a24a90)

   <h2>3. CNAME Record Exercise</h2>

   <h4>Steps:</h4>

1)  On DC-1, create a CNAME record for the host "search" and point it to "www.google.com".
2)  On Client-1, attempt to ping “search”. You'll notice that it resolves the CNAME record to Google's IP address.
3)  Use nslookup on Client-1 to query the “search” record and observe the CNAME result pointing to www.google.com.

  <h3>Key Learning:</h3>
<h4></h4>This exercise teaches you how to configure CNAME (Canonical Name) records, which allow one hostname to act as an alias for another. It also reinforces the concept of how DNS resolves multiple types of records.</h4>


![image](https://github.com/user-attachments/assets/d33c4f68-935c-4090-83c0-9a09ad5525e2)

<h2>Conclusion</h2>
By completing these exercises, you develop an intuitive understanding of common DNS record types and how DNS resolution works on both the client and server sides. You also gain hands-on experience with managing DNS caching and resolving issues related to DNS resolution.


