---
marp: true
backgroundColor: #F1F3F3
color: #232F3E
style: |
  section.titleslide h1 {
    color: #ffffff;
  }
  section.titleslide h2 {
    color: #ffffff;
  }
  section.titleslide p {
    color: #ffffff;
  }
  a {
    color: #ff6633;
  }
  video.inslide {
    position: absolute;
    width: 80%;
    height: 80%;
    left: 10%;
  }
  footer {
    position: absolute;
    left: 40%;
    bottom: 30px;
    font-size: 14px;
  }
  img {
    background-color: transparent!important;
  }
header: 'This is code. Fork it on [github.com/ojacques](https://github.com/ojacques)'
footer: '© 2022, Amazon Web Services, Inc. or its Affiliates.'
---

<!-- _class: titleslide -->

![bg](bg_title.jpg)

<br/>
<br/>
<br/>
<br/>

# CDK

L'infrastructure-as-code avec son langage favori

Olivier JACQUES
AWS ProServe

![AWS User Group Grenoble](aws-ug.png)

<!-- 

-->

---

Les façons de provisionner de l'infrastructure

* **Manuel** : Documents Word, Wikis, demande-a-robert-il-l'a-déjà-fait
* **Scripté** : `#!/bin/bash`
* **Déclaratif** : CloudFormation, Terraform
* **Générateurs** : Troposphere, GoFormation
* **Abstractions** : AWS CDK, Pulumi

<!-- 

-->

---

<!-- _class: titleslide -->
![bg](bg_divider.jpg)

# AWS Cloud Development Kit

---

Programmez l'infrastructure en Python, Typescript, Javascript, Java, C#, Go

![CDK screenshot](cdk.jpg)

---

# 3 projets

* AWS CDK
* CDK for Terraform
* Cloud Development Kit for Kubernetes - CDK8s

Tous basés sur JSSI

---

# 3 cycles

* [`Python, TS, JS, Java, C#, Go`] => **AWS CDK** => CloudFormation
* [`Python, TS, JS, Java, C#, Go`] => **CDKTF** => Terraform HCL
* [`Python, TS, JS, Java, C#, Go`] => **CDK8s** => Kubernetes manifests

---

# 6 GIT commands

* `git branch my_new_feature`
* `git add .`
* `git commit -m "New: AWS RDS infrastructure is now managed as code"`
* `git push -u origin my_new_feature`
* `git checkout main`
* `git pull`

---

# Séquence

* 📘 `cdktf init`
* 🛠️ `npm run build`
* 🏭 `cdktf synth`
* 🔍 `cdktf diff`
* 🚀 `cdktf deploy`

---

<!-- _class: titleslide -->

![bg](bg_title.jpg)

# Merci

🐤 @ojacques2
