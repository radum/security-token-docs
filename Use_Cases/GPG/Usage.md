# Transferring the key to your laptop

Transferring secret keys around always raises some eyebrows, but the reality is many of us make commits from multiple computers. As long as you protect the key in transit, this should be relatively secure. Firstly, export it into a couple of files:

```
gpg --export 04D1111C > key-pub.asc
gpg --export-secret-keys 04D1111C > key-sec.asc
```

Then securely transfer those files to your laptop (scp is a good choice) and run:

```
gpg --import key-pub.asc
gpg --import key-sec.asc
```

When you're done, securely delete the .asc files on both computers (I use shred but there are other options).
