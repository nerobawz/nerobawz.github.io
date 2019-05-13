import re import time import socket import json,operator

with open('incidents.json') as json_file:

`   data = json.load(json_file)`

def first(sock):

`   res = sock.recv(250).decode('utf-8')`

`   src_ips = {}`
`   for ticket in data['tickets']:`
`       if( ticket['src_ip'] in src_ips):`
`           src_ips[ticket['src_ip']] = src_ips[ticket['src_ip']] + 1`
`       else:`
`           src_ips[ticket['src_ip']] = 1`

`   common = max(src_ips.items(), key=operator.itemgetter(1))[0]`
`   print(common)`
`   sock.send((common + "\n").encode('utf-8'))`
`   res = sock.recv(250).decode('utf-8')`
`   print(res)`
`   res = res.split('\n')`
`   return res`

def which(ip):

`   dests = []`
`   for ticket in data['tickets']:`
`       if(ticket['src_ip'] == ip):`
`           if(ticket['dst_ip'] not in dests):`
`               dests.append(ticket['dst_ip'])`

`   print(len(dests))`
`   return (str(len(dests))+"\n").encode('utf-8')`

def second(sock, first_res):

`   print(first_res)`
`   ip = re.search(r'\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}',`
`                  first_res[-2]).group()`
`   ans = which(ip)`
`   sock.send(ans.encode('utf-8'))`
`   res = sock.recv(250).decode('utf-8')`
`   res.split('\n')`
`   return res`

def third(sock, ans):

`   ans = str(ans) + "\n"`
`   sock.send(ans.encode('utf-8'))`
`   res = sock.recv(250).decode('utf-8')`
`   res = res.split('\n')`
`   return res`

if __name__ == '__main__':

`   port = 63299`
`   host = "2018shell1.picoctf.com"`

`   # Loop over third question`
`   # for third_ans in [float(j)/100 for j in range(110, 1501, 1)] :`
`   for third_ans in [float(j)/100 for j in range(110, 1501, 1)] :`

`       print("Trying", third_ans)`

`       try:`
`           sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)`
`       except socket.error as err:`
`           print("socket creation failed with error %s" % (err))`
`       sock.connect((host, port))`

`       first_res = first(sock)`

`       second_res = second(sock, first_res)`

`       third_res = third(sock, third_ans)`
`       print("THIRD----->", third_res)`

`       if third_res[0] == "Correct!":`
`           break`

`       sock.close()`

time.sleep(1.0)