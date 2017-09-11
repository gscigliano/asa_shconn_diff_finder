# asa_shconn_diff_finder
points out differences in connections on 2 sh conns, to see which connections are moving data

<pre>
say you have something like this:
cat 1
TCP OUTSIDE  1.1.1.1:61638 DMZ  2.2.2.2:443, idle 0:01:35, bytes 514, flags UIOB
TCP OUTSIDE  1.1.1.1:61637 DMZ  2.2.2.2:443, idle 0:01:12, bytes 8917, flags UIOB
TCP OUTSIDE  1.1.1.1:61520 DMZ  2.2.2.2:443, idle 0:01:13, bytes 14901, flags UIOB
TCP OUTSIDE  1.1.1.1:8314 DMZ  2.2.2.2:443, idle 0:01:12, bytes 17134, flags UIOB
TCP OUTSIDE  1.1.1.1:61444 DMZ  2.2.2.2:443, idle 0:01:13, bytes 54730, flags UIOB
TCP OUTSIDE  1.1.1.1:61424 DMZ  2.2.2.2:443, idle 0:01:12, bytes 74751, flags UIOB
TCP OUTSIDE  1.1.1.1:51330 DMZ  2.2.2.2:443, idle 0:01:16, bytes 754923, flags UIOB
TCP OUTSIDE  1.1.1.1:54587 DMZ  2.2.2.2:443, idle 0:01:17, bytes 631819, flags UIOB
cat 2
TCP OUTSIDE  1.1.1.1:61638 DMZ  2.2.2.2:443, idle 0:00:1, bytes 515, flags UIOB
TCP OUTSIDE  1.1.1.1:61637 DMZ  2.2.2.2:443, idle 0:01:12, bytes 8917, flags UIOB
TCP OUTSIDE  1.1.1.1:61520 DMZ  2.2.2.2:443, idle 0:01:13, bytes 14901, flags UIOB
TCP OUTSIDE  1.1.1.1:8314 DMZ  2.2.2.2:443, idle 0:01:12, bytes 17134, flags UIOB
TCP OUTSIDE  1.1.1.1:61444 DMZ  2.2.2.2:443, idle 0:01:13, bytes 54730, flags UIOB
TCP OUTSIDE  1.1.1.1:61424 DMZ  2.2.2.2:443, idle 0:01:12, bytes 74751, flags UIOB
TCP OUTSIDE  1.1.1.1:54587 DMZ  2.2.2.2:443, idle 0:01:17, bytes 631819, flags UIOB
TCP OUTSIDE  1.1.1.1:16666 DMZ  2.2.2.2:443, idle 0:00:1, bytes 631819, flags UIOB

######### python scr 1 2

found difference in conn: TCP OUTSIDE 1.1.1.1:61638 DMZ 2.2.2.2:443
BEFORE
{'idle': '0:01:35', 'bytes': '514'}
AFTER
{'idle': '0:00:1', 'bytes': '515'}

connection TCP OUTSIDE 1.1.1.1:51330 DMZ 2.2.2.2:443 is gone


found new conn: TCP OUTSIDE 1.1.1.1:16666 DMZ 2.2.2.2:443

</pre>

