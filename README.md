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
	<em><code>C++ Rendering/Graphics project template with GLFW, Dear ImGUI, and OpenGL 4.1.
</code></em>
</p>
<p align="center">
	<img src="https://img.shields.io/github/license/djoezeke/GLFWTem?style=default&logo=opensourceinitiative&logoColor=white&color=0080ff" alt="license">
	<img src="https://img.shields.io/github/last-commit/djoezeke/GLFWTem?style=default&logo=git&logoColor=white&color=0080ff" alt="last-commit">
	<img src="https://img.shields.io/github/languages/top/djoezeke/GLFWTem?style=default&color=0080ff" alt="repo-top-language">
	<img src="https://img.shields.io/github/languages/count/djoezeke/GLFWTem?style=default&color=0080ff" alt="repo-language-count">
</p>

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
- [📃 License](#-license)

</details>

## 📍 Overview

This repository template should allow for a fast and hassle-free kick start of your next GLFW project using CMake.
Thanks to [GitHub's nature of templates](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template), you can fork this repository without inheriting its Git history.

The template starts out very basic, but might receive additional features over time:

- Basic CMake script to build your project and link GLFW on any operating system
- Basic [GitHub Actions](https://github.com/features/actions) script for all major platforms

### What is this?

C++ GLFW project template with GLFW, Dear ImGUI, and OpenGL 4.1.
This repository is a template OpenGL project configured using CMake.
It supports cross-platform builds, and provides a good starting point to begin OpenGL development.

### For whom is this for?

- Prototyping
- Getting started with game programming
- Getting started with graphics programming

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

## 🚀 Getting Started

1. Install [Git](https://git-scm.com/downloads) and [CMake](https://cmake.org/download/). Use your system's package manager if available.

## ☑️ Prerequisites

This project leverages several modern libraries and tools to streamline development, building, and documentation.

### 📚 Libraries

<div>
   <table> 
      <thead> 
         <tr> <th>Library</th> <th>Purpose</th> <th>Details</th></tr> 
      </thead> 
      <tbody> 
         <tr> 
            <td><a href="https://github.com/glfw/glfw">GLFW</a></td> <td>Window/Input</td> <td>Cross-platform window and input management</td> 
         </tr> 
         <tr> 
            <td><a href="https://www.opengl.org/">OpenGL</a></td> <td>Graphics API</td> <td>Hardware-accelerated rendering</td> 
         </tr> 
         <tr> 
            <td><a href="https://github.com/ocornut/imgui">ImGui</a></td> <td>Graphical User Interface</td> <td>Immediate Mode Graphical User Interface</td> 
         </tr> 
         <tr> 
            <td><a href="https://github.com/g-truc/glm">GLM</a></td> <td>OpenGL Math Library</td> <td>OpenGL Mathematics (vectors, matrices, etc.)</td> 
         </tr> 
         <tr> 
            <td><a href="https://github.com/djoezeke/glad">Glad</a></td> <td>OpenGL Loader</td> <td>OpenGL function loaders</td> 
         </tr> 
         <tr> 
            <td><a href="https://github.com/nothings/stb">Stb Image</a></td> <td>Image Loading</td> <td>Header-only image loading library</td> 
         </tr> 
      </tbody> 
   </table> 
</div>

### 🧑‍💻 Compilers

<div>
   <table> 
      <thead> 
         <tr> <th>Compiler</th> <th>Platforms</th> <th>Minimum Version</th></tr> 
      </thead> 
      <tbody> 
         <tr> 
            <td><a href="https://clang.llvm.org/">Clang</a></td> <td>Linux/Windows/MacOs</td> <td>10</td> 
         </tr> 
         <tr> 
            <td><a href="https://visualstudio.microsoft.com/vs/features/cplusplus/">MSVC</a></td> <td>Windows Only</td> <td>2019</td> 
         </tr> 
         <tr> 
            <td><a href="https://gcc.gnu.org/">GNU/MinGW</a></td> <td>Linux/Windows/MacOs</td><td>9</td> 
         </tr> 
      </tbody> 
   </table> 
</div>

### 🛠️ Build Tools

<details closed>
   <summary> <a href="https://cmake.org/">Cmake - Cross-platform build configuration </a></summary>
</details>

<details closed>
   <summary> <a href="https://www.gnu.org/software/make/">Make - Linux/macOS build Automation</a></summary>
</details>

<details closed>
   <summary> <a href="">Script</a></summary>
</details>

### 🧰 Additional Tools

- [Git](https://git-scm.com/) – Version control and submodule/dependency management
- [Doxygen](https://doxygen.org/) – (Optional) Generate code documentation
- [Ninja](https://ninja-build.org/) – (Optional) Faster alternative build backend for CMake
- [Conan](https://conan.io/) for install packages (optional)

## ⚙️ Installation

### Using [CMake](https://cmake.org/)

<details closed>
<summary>Configuring and Building</summary>

</details>

### Using [Make](https://www.gnu.org/software/make/)

<details closed>
<summary>Configuring and Building</summary>

</details>

## 🤖 Usage

## 🧪 Testing

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

## 🙌 Acknowledgments

We would like to express our gratitude to the following projects and individuals whose work made this project possible:

- [GLFW](https://www.glfw.org/) – for providing a robust, cross-platform OpenGL framework.
- [OpenGL](https://www.opengl.org/) – for the graphics API.
- [Dear ImGui](https://github.com/ocornut/imgui) – for the immediate mode GUI library (if used).
- The open-source community for their invaluable libraries, tutorials, and support.
- Special thanks to all contributors, testers, and users who provided feedback and suggestions.

If you feel your work should be acknowledged here, please open an issue or pull request.

### References

- [SFMLTem](https://github.com/djoezeke/SFMLTem/) : A SFML Starter Template with [SFML](https://github.com/SFML/SFML/) and [ImGui](https://github.com/ocornut/imgui).
- [SDLTem](https://github.com/djoezeke/SDLTem/) : A SDL Starter Template with [SDL](https://github.com/libsdl-org/sdl) and [ImGui](https://github.com/ocornut/imgui).
- [CppStarter](https://github.com/djoezeke/CppStarter/) : A C/C++ Starter Template.

### More Reading

- [Official CMake Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)
- [Dear ImGui with Conan](https://blog.conan.io/2019/06/26/An-introduction-to-the-Dear-ImGui-library.html)
- [Dear ImGui with Vulkan](https://frguthmann.github.io/posts/vulkan_imgui/)
- [GLFW Documentation](https://www.glfw.org/docs/latest/)
- [OpenGL Tutorials](https://learnopengl.com/)
- [GLM Manual](https://glm.g-truc.net/0.9.9/index.html)

## 📃 License

This project is protected under the [MIT](LICENSE) License.
For more details, refer to the [LICENSE](LICENSE) file.

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="
      https://api.star-history.com/svg?repos=GLFWTem/djoezeke&type=Date&theme=dark
    "
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="
      https://api.star-history.com/svg?repos=GLFWTem/djoezeke&type=Date
    "
  />
  <img
    alt="Star History Chart"
    src="https://api.star-history.com/svg?repos=GLFWTem/djoezeke&type=Date"
  />
</picture>
