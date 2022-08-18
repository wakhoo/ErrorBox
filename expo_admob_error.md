expo admob error

main.js

```
import {
  AdMobBanner,
  AdMobInterstitial,
  PublisherBanner,
  AdMobRewarded,
  setTestDeviceIDAsync,
} from 'expo-ads-admob';
//from 'expo'에서도 동일한 에러 발생
```

```java script

{Platform.OS === 'ios' ? (
                <AdMobBanner
                  bannerSize="fullBanner"
                  adUnitID="ca-app-pub-4786552475877219/4742911129"
                  style={styles.banner}
                  servePersonalizedAds = {true} // true or false
                   />
            ) : (
              <AdMobBanner
                  bannerSize="fullBanner"
                  adUnitID="ca-app-pub-4786552475877219/7752217842"
                  style={styles.banner}
                  servePersonalizedAds = {true} // true or false
                   />
            )}
```

위 부분 주석 처리시 화면 정상적으로 출력되는 걸 확인하였습니다.

app.json

```jsx
{
  "expo": {
    "name": "sparta",
    "slug": "sparta",
    "version": "1.0.0",
    "orientation": "portrait",
    "icon": "./assets/icon.png",
    "userInterfaceStyle": "light",
    "splash": {
      "image": "./assets/splash.png",
      "resizeMode": "contain",
      "backgroundColor": "#ffffff"
    },
    "plugins": [
      [
        "expo-ads-admob",
        {
          "userTrackingPermission": "This identifier will be used to deliver personalized ads to you."
        }
      ]
    ],
    "updates": {
      "fallbackToCacheTimeout": 0
    },
    "assetBundlePatterns": [
      "**/*"
    ],
    "ios": {
      "supportsTablet": true,
      "buildNumber": "1.0.0",
      "bundleIdentifier": "com.jeon.sparta",
      "config": {
        "googleMobileAdsAppId": "ca-app-pub-4786552475877219~6798228829"
      }
    },
    "android": {
      "adaptiveIcon": {
        "foregroundImage": "./assets/adaptive-icon.png",
        "backgroundColor": "#FFFFFF"
      },
      "package": "com.jeon.sparta",
      "versionCode": 1,
      "config": {
        "googleMobileAdsAppId": "ca-app-pub-4786552475877219~3242127199"
      }
    },
    "web": {
      "favicon": "./assets/favicon.png"
    }
  }
}
```

### 발생 에러


### 에드몹 승인

에드몹은 승인되었다고 이메일을 받았습니다.
