<!-- Network Security Groups -->
<h2>Network Security Groups (NSGs)</h2>
<p>
  Network Security Groups (NSGs) are critical for controlling inbound and outbound traffic to your Azure Virtual Machines. Proper configuration ensures your Active Directory lab remains secure while allowing necessary services.
</p>

<h3>Recommended NSG Configuration</h3>
<ul>
  <li>🔹 <strong>Domain Controller (DC-1)</strong>
    <ul>
      <li>Inbound Rules:
        <ul>
          <li>RDP (TCP 3389) - Allow from your IP only</li>
          <li>DNS (TCP/UDP 53) - Allow from Client subnet</li>
          <li>LDAP (TCP 389) - Allow from Client subnet</li>
          <li>Kerberos (TCP/UDP 88) - Allow from Client subnet</li>
          <li>SMB (TCP 445) - Allow from Client subnet if file sharing needed</li>
        </ul>
      </li>
      <li>Outbound Rules: Default allow all</li>
    </ul>
  </li>
  <li>🔹 <strong>Client VM (Client-1)</strong>
    <ul>
      <li>Inbound Rules:
        <ul>
          <li>RDP (TCP 3389) - Allow from your IP only</li>
        </ul>
      </li>
      <li>Outbound Rules:
        <ul>
          <li>Allow TCP/UDP 53 (DNS) to DC-1</li>
          <li>Allow TCP 88, 389, 445 to DC-1</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

<h3>Security Best Practices</h3>
<ul>
  <li>🛡 Limit RDP access to trusted IP addresses only.</li>
  <li>🛡 Apply the principle of least privilege for NSG rules.</li>
  <li>🛡 Monitor NSG logs in Azure to detect unauthorized access attempts.</li>
  <li>🛡 Separate subnets for Domain Controllers and Clients to isolate traffic.</li>
</ul>

<hr style="border-color:#00e0ff;"/>

<!-- Conclusion -->
<h2>Conclusion</h2>
<p>
  By following this guide, you now have a fully functional, isolated Active Directory lab environment in Azure. The combination of proper NSG configuration and domain setup ensures both usability and security for testing and learning purposes.
</p>

<!-- Footer -->
<p style="text-align:center; color:#888;">
  <p style="text-align:center; color:#888;">
  🔒 Crafted by <strong>Jonathan Taylor</strong>
</p>

</p>
