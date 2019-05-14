### [VueJS] vue-cli



VueJS와 같은 프론트엔드 프레임 워크의 궁극적인 목표는 백엔드 기반 프레임워크에서 뷰(화면을 일컫는 용어)를 완전히 분리하여 하나의 어플리케이션으로 만들고, 백엔드는 순수하게 API 서버 형태로 동작시키기 위함입니다.

vue-cli는 이러한 구성환경을 돕기위한 도구로 생각하면 됩니다.

vue-cli는 npm을 통해서 설치 가능하며, home directory 내에서 global하게 동작하기 때문에 -g 옵션을 통해 설치합니다

```bash
sudo npm install -g @vue/cli
```

<br>



설치가 완료된 후 

```bash
vue create 'project명'
```

명령어를 통해 프로젝트를 생성할 수 있으며, 해당 프로젝트에는 node_modules를 포함한 프로젝트의 뼈대 구조가 생성된 것을 볼 수 있습니다.

![image-20190513125116162](/Users/sungchan/Library/Application Support/typora-user-images/image-20190513125116162.png)