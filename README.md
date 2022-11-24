## 🌿 Jtisi-Meet Custom SDK 적용 🌿

### 🍀 [react-native-jitsi-meet](https://github.com/skrafft/react-native-jitsi-meet)에 Custom SDK 적용 🍀
- 1️⃣ [react-native-jitsi-meet](https://github.com/skrafft/react-native-jitsi-meet) `clone`
- 2️⃣ 내 `github` 에 올리기 (ExampleApp은 안올려두됨)
- 3️⃣ 최상위에서 `android` > `build.gradle(project)` 진입 후 설정
  > **_예제_** 👇
  ``` gralde
  repositories {
    maven {
      url "https://github.com/narvis2/Jitsi-Meet-Maven-Repository-5.1.0/raw/main/releases"
    }
    google()
    mavenCentral()
    jcenter()
  }
  
  dependencies {
    implementation ('org.jitsi.react:jitsi-meet-sdk:1.0.0') {
      transitive = true
    }
  }
  ```
  > **_✅ 참고 ✅_**
  > - 필요할 경우 최상위의 `android`에서 별도의 `Setting`이 필요
  > - 1️⃣ 최상위의 `android` > `wrapper` > `gradle-wrapper.properies` 에 진입하여 `distributionUrl` 변경
  >> - `distributionUrl=https\://services.gradle.org/distributions/gradle-6.9-all.zip` 로 변경
  > - 2️⃣ 최상위의 `android` > `gradle.properties`에 진입하여 `FLIPPER_VERSION` 수정
  >> - `FLIPPER_VERSION=0.99.0` 로 변경
    
- 4️⃣ `cd ExampleApp` 사용하여 `ExampleApp` 으로 진입
- 5️⃣ `ExampleApp`의 `package.json` 진입 후 설정
  > - `react-native-jitsi-meet` 라이브러리를 추가하는데 `Version`은 내가 올린 `Custom SDK`를 사용하고 있는 2️⃣ 번에서 올린 `github` 주소를 받아오도록 설정  
  
  > **_예제_** 👇
  ``` gralde
  "dependencies": {
    "react": "16.11.0",
    "react-native": "0.62.2",
    "react-native-jitsi-meet": "git+https://github.com/narvis2/Jitsi-Meet-Example.git"
  },
  ```
- 6️⃣ `ExampleApp`에서 `npm install`을 실행하여 `node_modules` 생성
  > **_예제_** 👇
  ``` terminal
  npm --legacy-peer-deps install
  ```
- 7️⃣ `Android Studio`를 실행하여 `local.properties`에서 `ANDROID_SDK_LOCATION` 설정
- 8️⃣ `npm react-native run-android`를 실행하여 `Example` 앱 실행

### 🍀 일반 Project에 Jitsi-Meet Custom SDK 적용 🍀
- 1️⃣ `android` 폴더 진입
- 2️⃣ `build.gradle(project)`진입
- 3️⃣ 내가 만든 `Custom SDK` 적용
  > **_예제_** 👇
  ``` gradle
  repositories {
    maven {
      url "https://github.com/narvis2/Jitsi-Meet-Maven-Repository-5.1.0/raw/main/releases"
    }
    google()
    mavenCentral()
    jcenter()
  }
  
  dependencies {
    implementation ('org.jitsi.react:jitsi-meet-sdk:1.0.0') {
      transitive = true
    }
  }
  ```
