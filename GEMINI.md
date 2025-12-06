# Gemini Added Memories
## 1. Communication Language Requirements
- Please communicate with me in Chinese.
- The user requests that all subsequent responses be presented in Chinese.

## 2. Code Development Specifications
1. When writing any code, priority must be given to developing based on the existing project code; no code should be created out of thin air or fabricated randomly.
2. The development process must follow these steps: first analyze the existing project code, then plan the development approach, and finally proceed with development. Each step of the replacement process can only be saved after receiving my approval.
3. When modifying code, prioritize the "principle of minimal modification" and do not replace large sections of code that do not require modification.
4. When writing Java code, you must first import the required packages, and then use the class names directly in the code. Under no circumstances should you use fully qualified names (such as `com.example.MyClass.someMethod()`) directly in the code.
5. Before creating a variable, you must first import the package corresponding to the variable's class.
6. Make only one modification at a time, wait for confirmation before proceeding to the next step, and prohibit generating multiple code blocks at once for the user to confirm and accept.

## 3. Tool Call and File Modification Rules
- Unless the user explicitly asks to replace or write code, do not generate `replace` (replacement) or `write_file` (file writing) tool calls. Before generating code that modifies files, you must first obtain the user's explicit textual confirmation.

## 4. Requirements for Question Answering and Solution Output
1. When answering questions, the solution must be explained clearly, completely and in detail; it is not allowed to answer with only a few words.
2. When the user requests a proposal, it is essential to provide a complete explanation of the problem background, implementation ideas, and specific plan. A mere simple conclusion is not acceptable.

## 5. Library and API Usage Specifications
- Before calling any method in the library, it is necessary to confirm that the method (API) actually exists in the library and cannot be guessed out of thin air.

## 6. Special Requirements for Android Development
- In Android development, priority should be given to ensuring the correctness of functions and the integrity of the UI flow. Tasks such as data querying and network requests can be offloaded to sub-threads for execution, and the results must be returned to the main thread after execution is completed.

## 7. Method Change and Maintenance Rules
- When a method is modified, added, or deleted, all relevant parts that use the method must be updated synchronously. It is prohibited to have situations where calls to a deleted method still exist after the method has been removed, or where calls to a modified method remain unupdated, leading to invocation exceptions.

## 8. General Operation Taboos
1. Never assume anything. For any uncertain information (such as method names, file contents, or the existence of an API), you must first confirm it by reviewing and verifying before proceeding to the next step.
2. When modifying the code, it must be reviewed and approved by me before being written into the file. Additionally, excessive comments should not be added when modifying the code, and all comments must be in Chinese; in all operations, the identification of "AI as the author" is strictly prohibited.

## Gemini Added Memories
- During Android development, first sort out the core version configurations of the current project: clarify the minimum supported API version (minSdkVersion), target API version (targetSdkVersion), and compile API version (compileSdkVersion), and verify the compatibility between the matching JDK version and Gradle version. Subsequently, develop using the MVP architecture, strictly dividing the Model layer (responsible for data acquisition, parsing, local storage/network request logic), View layer (focusing on UI rendering and user interaction responses, communicating with the Presenter through interfaces), and Presenter layer (undertaking business logic scheduling, isolating the View and Model for two-way decoupling). Ensure dependency inversion and interface-based communication between layers. Meanwhile, all permissions must meet dual configurations: ① Declare necessary permissions (such as dangerous permissions and normal permissions) in AndroidManifest.xml; ② For Android 6.0 (API 23) and above, dynamically apply for dangerous permissions in the page through code, and supporting implement permission application callbacks and permission denial prompts (including logic to guide users to the settings page to enable permissions). Select dependent libraries (such as network request and serialization tools) based on the confirmed version environment to avoid compilation/runtime exceptions caused by version incompatibility or incomplete permission configuration.

- When issuing commands such as reading code, re - reading code, or updating your memory, you must re - "read" the specified code and refresh the AI's memory storage.
