[Category:OverTheWire-Natas](/Category:OverTheWire-Natas "wikilink")

Username: natas11 U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK URL:
<http://natas11.natas.labs.overthewire.org>

we know that xor is very weak and with the plaintext we can solve it
like: key xor plain = encrypted; key xor encrypted = plain; plain xor
encrypted = key;

so lets get the key

`> function xor_encrypt1($in) {  `

php { $text = $in; php { $key = json_encode(array(
"showpassword"=\>"no", "bgcolor"=\>"\#ffffff")); php { $outText = '';
php { // Iterate through each character php {
for($i=0;$i\<strlen($text);$i++) { php { $outText .= $text\[$i\] ^
$key\[$i % strlen($key)\]; php { } php { return $outText; php { } php \>
echo
xor_encrypt1(base64_decode("ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSEV4sFxFeaAw%3D"));
qw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jqw8Jq

we see the key repeated so it is: qw8J

php \> function xor_encrypt($in) { php { $key = "qw8J"; php { $text =
$in; php { $outText = ''; php { php { // Iterate through each character
php { for($i=0;$i\<strlen($text);$i++) { php { $outText .= $text\[$i\] ^
$key\[$i % strlen($key)\]; php { } php { php { return $outText; php { }
php \> $solution = json_encode(array( "showpassword"=\>"yes",
"bgcolor"=\>"\#ffffff")); php \> echo $solution php \> ;
{"showpassword":"yes","bgcolor":"\#ffffff"} php \> echo
base64_encode(xor_encrypt($solution));
ClVLIh4ASCsCBE8lAxMacFMOXTlTWxooFhRXJh4FGnBTVF4sFxFeLFMK

now this will become our cookie save and refresh

The password for natas12 is EDXp0pS26wLKHZy1rDBPUZk0RKfLGIR3