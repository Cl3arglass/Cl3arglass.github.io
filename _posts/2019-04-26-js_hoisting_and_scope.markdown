---
layout: post
title:      "JS Hoisting and Scope"
date:       2019-04-26 16:16:15 +0000
permalink:  js_hoisting_and_scope
---


What is "hoisting" in JS? - What is "scope" in JS? - How do ES6 syntaxes such as `let` and `const` affect hoisting and scope, compared to `var`?

First before we tackle hoisting lets talk about scope. The internet says there are two types of scope; Local and Global.

					// code here can NOT use plantName

					function myFunction() {
						var plantName = "Ficus";

						// code here CAN use plantName

					}
					
So, inshort variables are only usable within the functions they are declared. Within these functions, the type of variable you declare is important because their values are hoisted in different ways.

The OED definition of hoisting is: "Hoisting is the JavaScript interpreter’s action of moving all variable and function declarations to the top of the current scope." 

Be advised, JS has a few quirks that might leave you head scratching.  Let's go through each variable type and point out their key differences.

"var": Javascript places these variables at the top of the function scope, even if you declared them at the bottom. But be carefull, although these variables are technically available, you will get undefined if you try and return them before they are initialized.

"let" : Is very similar to "var" but as per ES6 it has block-scope so it is available throughout all of the block that it is declared.

"const": This is like "let" but with more rules. These variables cannot be reassigned and must be initialized at the time of declaration.

Most people use var sparingly, let with iteration, and const to avoid bugs.
