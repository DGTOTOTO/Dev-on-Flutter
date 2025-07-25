# PA3 Ask Me Anything

<figure><img src="../.gitbook/assets/PA3_Ask Me Anything.PNG" alt="" width="188"><figcaption></figcaption></figure>

```dart
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  return runApp(MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  final List<String> stateList = ['state_emm', 'state_no', 'state_yes'];
  String stateDefault = 'state_dash';
  String state = 'state_dash';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: const Color.fromARGB(255, 57, 61, 65),
        appBar: AppBar(
          title: Text(
            'Ask Me Anything',
            style: TextStyle(fontFamily: 'Gill Sans', color: Colors.white),
          ),
          backgroundColor: const Color.fromARGB(255, 61, 68, 70),
        ),
        body: Padding(
          padding: const EdgeInsets.all(24.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            spacing: 40,
            children: [
              Stack(
                alignment: Alignment.center,
                children: [
                  SizedBox(
                    width: 400,
                    height: 400,
                    child: Image.asset('images/theBall.png'),
                  ),

                  Positioned(
                    bottom: 400 - 172 - 100,
                    child: SizedBox(
                      width: 100,
                      height: 100,
                      child: Image.asset('images/$state.png'),
                    ),
                  ),
                ],
              ),
              TextButton(
                onPressed: () {
                  setState(() {
                    // state = stateDefault;
                    state = stateList[Random().nextInt(3)];
                    print('state: $state');
                  });
                },
                style: TextButton.styleFrom(
                  backgroundColor: Colors.black,
                  foregroundColor: Colors.white,
                ),
                child: Text('Hold to talk'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

```

## APPENDIX

### images

{% file src="../.gitbook/assets/PA3_images.zip" %}
