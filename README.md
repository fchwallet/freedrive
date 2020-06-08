# Freedrive Protocol
Layer II Protocol, Safety & Simple base on original  [SLP.](https://github.com/simpleledger/slp-specifications)  
Freedrive operate on non-standard UTXOs,which can include any state of your services.  
Own your own data.
## Transaction struture

**Transaction inputs**: Any number of inputs or content of inputs, in any order.  
**Transaction outputs**:
<table>
<tr>
  <td><b>v<sub>out</sub></b></td>
  <td><b>OutputScript </b></td>
  <td><b>Coin<br>amount </b></td>
</tr>
  <tr>
    <td>...</td>
   <td>
   <b>Lockingscript<sup>1</sup></b>:</br>
   'OP_DUP OP_HASH160 986b57ea26555d28c OP_EQUALVERIFY OP_CHECKSIG' (0 to ∞ bytes)<br/>   
   OP_RETURN<sup>2</sup>: '\x6a' (1 byte, ascii)<br/>
   <b>metadata:</b></br>
   &lt;protocol_type: 'FOCP'&gt; (4 bytes, ascii)<br/>
   &lt;protocol_id: '\x02'&gt; (1 byte integer)<br/>
   &lt;protocol_version: '\x01'&gt; (1 byte integer)<br/>
   &lt;data_hash: &gt; (32 bytes, sha256(data))<br/>
   &lt;encrypt: '0' / '1'&gt; (1 byte integer)<br/>
   &lt;encrypted_pwd: (4 to 32 bytes ascii,if encrypt is true)<br/>
   </td>
   <td>>0</td>
  </tr>
  
  <tr>
    <td>...</td>
    <td>Any</td>
   <td>>any</td>
  </tr>
  
  <tr>
    <td>...</td>
    <td>
    OP_FALSE : '\x00' (1 byte, ascii)<br>
    OP_RETURN<sup>3</sup>: '\x6a' (1 byte, ascii)<br> 
   <b>data:</b></br>
   &lt;data: &gt; (0 to ∞ bytes)<br/>
    </td>
    <td>0</td>
  </tr>
 
</table>

<sup>1. The <b>Lockingscript</b> can be any valid script by combination op_codes, which controls who can operate the data, by spend the utxo. </sup>  
<sup>2. The OP_RETURN should be <b>metadata</b> for specific services. </sup>   
<sup>3. The OP_FALSE OP_RETURN vout should be <b>data</b> itself for specific services. </sup>   

## Tools  
coming soon
```
1. UTXO(includes non-standard) management tools.  
2. write complex script for non-standard transaction outputscript.
```
