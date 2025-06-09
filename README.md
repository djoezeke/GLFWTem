```console
███████ ██     ██████ ██       ██   ████████ ██████   ███   ███  ██████ ██      ████  ████████ ██████
██      ██     ██     ██       ██      ██    ██      ██ ██ ██ ██ ██  ██ ██     ██  ██    ██    ██
██  ███ ██     █████  ██  ███  ██      ██    █████   ██  ███  ██ ██████ ██     ██████    ██    ██████
██   ██ ██     ██     ██ ██ ██ ██      ██    ██      ██       ██ ██     ██     ██  ██    ██    ██
███████ ██████ ██      ███   ███       ██    ██████  ██       ██ ██     ██████ ██  ██    ██    ██████

◎ A Base Project Setup for GLFW/OpenGL
```

<p align="center"><h1 align="center">GLFW TEMPLATE</h1></p>
<p align="center">
	<em><code>C++ GUI/Graphics project template with GLFW, Dear ImGUI, and OpenGL 4.1.
</code></em>
</p>
<p align="center">
	<img src="https://img.shields.io/github/license/djoezeke/GLFWTem?style=default&logo=opensourceinitiative&logoColor=white&color=0080ff" alt="license">
	<img src="https://img.shields.io/github/last-commit/djoezeke/GLFWTem?style=default&logo=git&logoColor=white&color=0080ff" alt="last-commit">
	<img src="https://img.shields.io/github/languages/top/djoezeke/GLFWTem?style=default&color=0080ff" alt="repo-top-language">
	<img src="https://img.shields.io/github/languages/count/djoezeke/GLFWTem?style=default&color=0080ff" alt="repo-language-count">
</p>
<p align="center"><!-- default option, no dependency badges. -->
</p>
<p align="center">
	<!-- default option, no dependency badges. -->
</p>
<br>

<details><summary>Table of Contents</summary>

- [📍 Overview](#-overview)
- [👾 Features](#-features)
- [📁 Project Structure](#-project-structure)
- [🚀 Getting Started](#-getting-started)
  - [☑️ Prerequisites](#-prerequisites)
  - [⚙️ Installation](#-installation)
  - [🤖 Usage](#🤖-usage)
  - [🧪 Testing](#🧪-testing)
- [📌 Project Roadmap](#-project-roadmap)
- [🔰 Contributing](#-contributing)
- [🙌 Acknowledgments](#-acknowledgments)
- [🎗 License](#-license)

</details>


---

## 👾 Features


- Sources, headers and mains separated in distinct folders
- Use of modern [CMake](https://cmake.org/) for much easier compiling
- Continuous integration via [GitHub Actions](https://help.github.com/en/actions)


---

## Dependencies

### Libraries
- [GLAD]() - OpenGL loader and wrapper
- [GLM]() - GL mathematics library
- [GLFW]() - API for creating windows, contexts and handling input events
- [Imgui]() - Immediate Mode Graphical User Interface
### Compilers

- Clang C/C++ Compiler
- Microsoft compiler (MSVC)
- MinGW Compiler (GNU)

### Build Tools
- [CMake](https://cmake.org/)

   <details closed>
   <summary>Cmake Build Configuration/Compilation</summary>
   </details>

- [Makefile]()

   <details closed>
   <summary>Makefile Build Configuration/Compilation</summary>
   </details>

- [Scripts]()

   <details closed>
   <summary>Scripts Build Configuration/Compilation</summary>
   </details>

### Others 
* [Conan](https://conan.io/) for install packages
* [Git](https://git-scm.com/) for cmake automatic dependencies
* [Doxygen](https://doxygen.org/) for generate documentation (optional)

## 🔰 Contributing

- **💬 [Join the Discussions](https://github.com/djoezeke/GLFWTem/discussions)**: Share your insights, provide feedback, or ask questions.
- **🐛 [Report Issues](https://github.com/djoezeke/GLFWTem/issues)**: Submit bugs found or log feature requests for the `GLFWTem` project.
- **💡 [Submit Pull Requests](https://github.com/djoezeke/GLFWTem/blob/main/CONTRIBUTING.md)**: Review open PRs, and submit your own PRs.

<details closed>
<summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your github account.
2. **Clone Locally**: Clone the forked repository to your local machine using a git client.
   ```sh
   git clone --recursive https://github.com/djoezeke/GLFWTem
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to github**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.
8. **Review**: Once your PR is reviewed and approved, it will be merged into the main branch. Congratulations on your contribution!
</details>

<details closed>
<summary>Contributor Graph</summary>
<br>
<p align="left">
   <a href="https://github.com{/djoezeke/GLFWTem/}graphs/contributors">
      <img src="https://contrib.rocks/image?repo=djoezeke/GLFWTem">
   </a>
</p>
</details>

---

## 🙌 Acknowledgments

### References


- [SDL](https://github.com/djoezeke/SDLTem/) Template : with [SDL](https://github.com/libsdl-org/sdl) and [ImGui](https://github.com/ocornut/imgui) 
- [SFML](https://github.com/djoezeke/SFMLTem/) Template : with [SFML](https://github.com/SFML/SFML) and [ImGui](https://github.com/ocornut/imgui)

- Inspirational templates : [CppProject](https://github.com/tweether/cpp-project), [ModernCppStarter](https://github.com/TheLartians/ModernCppStarter)

### More Reading

Here are some useful resources to learn more:

- [Official CMake Tutorial]()
- [Include ImGui with Conan](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html)
- [ Include ImGui with Vulkan](https://frguthmann.github.io/posts/vulkan_imgui/)

---

## 🎗 License

This project is protected under the [MIT](LICENSE) License. 
For more details, refer to the [LICENSE](LICENSE) file.

---
