<br>

# `Expose Api Locally: `

<br>

`Podman দিয়ে আমরা যেই  api রান করবো, সেইটা আমাদের router connected থাকা সকল device থেকে সেই api টি access করতে  পারবো । `

<br>

### **Step to follow with podman desktop:**

<br>


**i)** Open `podman desktop` then go to `Containers` Section then `Create` then 
`Containerfile or Docker file` . `এখানে, কাহিনী হচ্ছে আমরা আমরা একটা podman container বানাবো, হয়তো আগের থেকে existing কোন docker image  এর উপর বা আমরা একটা DockerFile থেকে বানাবো । DockerFile থেকে বানালে প্রথমে আমদের image make হবে তারপর podman container.`

**ii)** Router Setting গিয়ে port forwarding এ যাবো, যেখানে, service এর যেকোন নাম দিব । তারপর ip address দিতে হবে । এর পর আমাদের internal and external port  দিতে হবে । এক্ষেত্রে এখন, আমরা, podman এর Containers  এ যাবো, তারপর আমাদের কাক্ষিত Container এ গেলে আমরা Inspect নামে একটা section পাবো । সেখানে গেলে আমরা অনেক information পাবো, একটু নিচের দিকে যাবোঃ সেখানে আমরা, 

```bash
    "PortBindings": {
      "8000/tcp": [
        {
          "HostIp": "0.0.0.0",
          "HostPort": "8001"
        }
      ]
    },
```

"PortBindings" অংশে উল্লেখ করা হয়েছে যে আপনার API-এর অভ্যন্তরীণ পোর্ট (internal port) হলো **8000**, আর বাহ্যিক পোর্ট (external port) হলো **8001**। অর্থাৎ, বাহ্যিকভাবে 8001 পোর্টের মাধ্যমে অ্যাক্সেস করলে, এটি অভ্যন্তরীণভাবে 8000 পোর্টে সংযোগ করবে। 



