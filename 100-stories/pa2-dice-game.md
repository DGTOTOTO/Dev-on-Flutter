# PA2 Dice Game

<figure><img src="../.gitbook/assets/PA2_Dice Game.PNG" alt="" width="188"><figcaption></figcaption></figure>

<pre class="language-dart"><code class="lang-dart"><a data-footnote-ref href="#user-content-fn-1">import 'dart:math'</a>;
import 'package:flutter/material.dart';

void main() {
  return runApp(MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({super.key});
  @override
  State&#x3C;MyApp> createState() => _MyAppState();
}

class _MyAppState extends State&#x3C;MyApp> {
  int leftDice = 1;
  int rightDice = 1;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        backgroundColor: Colors.amber[400],
        appBar: AppBar(
          title: Text(
            'Dice Game',
            style: TextStyle(
              fontWeight: FontWeight.w600,
              fontFamily: 'Gill Sans',
            ),
          ),
          backgroundColor: Colors.amber[400],
          shape: Border(
            bottom: BorderSide(
              width: 3.0,
              color: const Color.fromARGB(19, 172, 129, 0),
            ),
          ),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            spacing: 30,
            children: [
              Row(
                children: [
                  Expanded(
                    child: TextButton(
                      child: Image.asset('images/dice$leftDice.png'),
                      onPressed: () {
                        <a data-footnote-ref href="#user-content-fn-1">setState(() {</a>
                          <a data-footnote-ref href="#user-content-fn-1">leftDice = Random().nextInt(6) + 1;</a>
                          <a data-footnote-ref href="#user-content-fn-1">print('Left Dice = $leftDice');</a>
                        <a data-footnote-ref href="#user-content-fn-1">});</a>
                      },
                    ),
                  ),
                  Expanded(
                    child: TextButton(
                      child: Image.asset('images/dice$rightDice.png'),
                      onPressed: () {
                        setState(() {
                          rightDice = Random().nextInt(6) + 1;
                          print('Right Dice = $rightDice');
                        });
                      },
                    ),
                  ),
                ],
              ),
              TextButton(
                onPressed: () {
                  setState(() {
                    leftDice = Random().nextInt(6) + 1;
                    rightDice = Random().nextInt(6) + 1;
                    while (leftDice == rightDice) {
                      leftDice = Random().nextInt(6) + 1;
                      print('opps!!!');
                    }
                    print('Right Dice = $rightDice');
                    print('Left Dice = $leftDice');
                  });
                },
                style: TextButton.styleFrom(
                  backgroundColor: Colors.blue,
                  foregroundColor: Colors.white,
                  iconSize: 20,
                ),
                child: Text('change all!'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

</code></pre>

## APPENDIX

### images

{% file src="../.gitbook/assets/PA2_images.zip" %}

[^1]: 
