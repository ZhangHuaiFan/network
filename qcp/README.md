This is a pair of utilities that implement a "quick copy" client/server. 
Quick doesn't really mean fast, just quick and dirty, in other words, no
authentication is used (so its the opposite of scp). It does not do recursion.

On the server where you want to receive the files, run the server qcps:

    cd /where/you/want/the/files
    qcps -p 1234

On the client where you want to send the files, run the qcp client:

    qcp -s host.xyz.net -p 1234 <file>

You can also run the client in a continuous mode where it reads filenames on stdin:

    iwatch incoming | qcp -s host.xyz.net -p 1234 

