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
## 📍 Overview

### What is this?

C++ GUI project template with SDL2, Dear ImGUI, and OpenGL 4.1.
This repository is a template OpenGL project configured using CMake.
It supports cross-platform builds, and provides a good starting point to begin OpenGL development.

### For whom is this for?

- Prototyping
- Getting started with game programming
- Getting started with graphics programming

---

## 👾 Features

- Modular project structure: sources, headers, and entry points are organized in distinct folders for clarity and scalability.
- Modern [CMake](https://cmake.org/) build system for easy, cross-platform compilation and dependency management.
- Out-of-the-box support for [GLFW](https://www.glfw.org/), [OpenGL 4.1](https://www.opengl.org/), [GLM](https://github.com/g-truc/glm), [GLAD](https://github.com/Dav1dde/glad), [Dear ImGui](https://github.com/ocornut/imgui), and [stb_image](https://github.com/nothings/stb).
- Continuous integration via [GitHub Actions](https://help.github.com/en/actions) for automated builds and testing.
- Example code for window creation, rendering loop, and GUI integration.
- Easily extensible for additional libraries or custom modules.
- Cross-platform: Windows, Linux, and macOS support.
- Optional support for [Conan](https://conan.io/) for advanced dependency management.
- Ready-to-use template for rapid prototyping, game development, or graphics research.

---

## 🧩 Dependencies

This project leverages several modern libraries and tools to streamline development, building, and documentation.

### 📚 Core Libraries

| Library                                                                 | Purpose                        | Details                                      |
|-------------------------------------------------------------------------|--------------------------------|----------------------------------------------|
| [GLFW](https://github.com/glfw/glfw)                                    | Windowing/Input                | Cross-platform window and input management   |
| [OpenGL](https://www.opengl.org/)                                       | Graphics API                   | Hardware-accelerated rendering               |
| [GLM](https://github.com/g-truc/glm)                                    | Math Library                   | OpenGL Mathematics (vectors, matrices, etc.) |
| [GLAD](https://github.com/Dav1dde/glad)                                 | OpenGL Loader                  | Generates OpenGL function loaders            |
| [stb_image](https://github.com/nothings/stb)                            | Image Loading                  | Header-only image loading library            |
| [Dear ImGui](https://github.com/ocornut/imgui)                          | GUI                            | Immediate Mode Graphical User Interface      |
| [Assimp](https://github.com/assimp/assimp) (optional)                   | Asset Import                   | Model/asset import library                   |

### 🛠️ Build Tools

| Tool                                                                    | Purpose                        | Details                                      |
|-------------------------------------------------------------------------|--------------------------------|----------------------------------------------|
| [CMake](https://cmake.org/)                                             | Build System                   | Cross-platform build configuration           |
| [Make](https://www.gnu.org/software/make/) (optional)                   | Build Automation               | Used on Linux/macOS for building             |
| [Conan](https://conan.io/) (optional)                                   | Dependency Management          | C++ package manager for libraries            |

### 🧑‍💻 Compilers

| Compiler                                                                | Platforms                      | Minimum Version                             |
|-------------------------------------------------------------------------|--------------------------------|---------------------------------------------|
| [Clang](https://clang.llvm.org/)                                        | Linux/Windows/macOS            | 10+                                         |
| [MSVC](https://visualstudio.microsoft.com/vs/features/cplusplus/)        | Windows                        | 2019+                                       |
| [GCC/MinGW](https://gcc.gnu.org/)                                       | Linux/Windows/macOS            | 9+                                          |

### 🧰 Additional Tools

- [Git](https://git-scm.com/) – Version control and submodule/dependency management
- [Doxygen](https://doxygen.org/) – (Optional) Generate code documentation
- [Ninja](https://ninja-build.org/) – (Optional) Faster alternative build backend for CMake

---

> **Note:**  
> All dependencies can be installed via your system package manager, or managed automatically using [Conan](https://conan.io/).  
> See the [Getting Started](#-getting-started) section for installation instructions.

---
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

We would like to express our gratitude to the following projects and individuals whose work made this project possible:

- [GLFW](https://www.glfw.org/) – for providing a robust, cross-platform OpenGL framework.
- [OpenGL](https://www.opengl.org/) – for the graphics API.
- [Dear ImGui](https://github.com/ocornut/imgui) – for the immediate mode GUI library (if used).
- The open-source community for their invaluable libraries, tutorials, and support.
- Special thanks to all contributors, testers, and users who provided feedback and suggestions.

If you feel your work should be acknowledged here, please open an issue or pull request.

---

## References

- **Project Templates:**
  - [SDL Template](https://github.com/djoezeke/SDLTem/) – C++ template with [SDL](https://github.com/libsdl-org/sdl) and [ImGui](https://github.com/ocornut/imgui)
  - [SFML Template](https://github.com/djoezeke/SFMLTem/) – C++ template with [SFML](https://github.com/SFML/SFML) and [ImGui](https://github.com/ocornut/imgui)
  - [CppProject](https://github.com/tweether/cpp-project) – General C++ project structure inspiration
  - [ModernCppStarter](https://github.com/TheLartians/ModernCppStarter) – Modern C++ project starter

- **Learning Resources:**
  - [Official CMake Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)
  - [Dear ImGui with Conan](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html)
  - [Dear ImGui with Vulkan](https://frguthmann.github.io/posts/vulkan_imgui/)
  - [GLFW Documentation](https://www.glfw.org/docs/latest/)
  - [OpenGL Tutorials](https://learnopengl.com/)
  - [GLM Manual](https://glm.g-truc.net/0.9.9/index.html)
  -

---

## 🎗 License

This project is protected under the [MIT](LICENSE) License. 
For more details, refer to the [LICENSE](LICENSE) file.

---
