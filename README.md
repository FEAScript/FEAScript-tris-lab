<img src="assets/tris-lab-icon.svg" width="80" alt="Tri's Lab by FEAScript logo: Tri, the FEAScript triangle robot">

# Tri's Lab by FEAScript

Playful, browser-only ways to meet the finite element method. Every result is a real [FEAScript](https://feascript.com) solve.

**Play it at [lab.feascript.com](https://lab.feascript.com).** No install, no account: open `index.html` in a browser, or serve the folder with `python3 -m http.server`.

The [FEAScript tutorials](https://feascript.com/#tutorials) link here from their "Tri's tip" callouts, and to single FEM Blocks missions with `blocks/?mission=<id>` (ids in `blocks/js/missions.js`). The pages share the FEAScript website's styles and scripts, loaded from `https://feascript.com/feascript-website.{css,js}`.

```
index.html          the Tri's Lab page
tris-lab.css        its styles (website tokens + pixel accents)
assets/             the Tri's Lab logo (tris-lab-icon.svg, tris-lab-logo.svg) and the page screenshots
critical-mesh/      Critical Mesh, a pixel-art heat-conduction game (see its README)
blocks/             FEM Blocks, a no-code block editor with missions for young learners
```

## FEM Blocks

Pixel-art Blockly blocks build a heat-conduction, creeping-flow or front-propagation (eikonal) model: a shape (bar or plate), a material (k), heaters (Q), edge conditions, and the solve and show steps. Run executes the generated FEAScript code, which is shown in the Code tab.

- **Missions**: nine missions (`js/missions.js`), each about one idea: a straight-line profile, a source term, 2D conduction, insulated edges, conductivity, convective cooling, mesh refinement, a lid-driven cavity and a freezing front (eikonal), plus a sandbox. Each goal is checked on the real FEAScript result.
- **Picture and Code**: the result as pixel art, and the FEAScript code the blocks write. Clicking a block lights up its lines of code.
- **The math**: first the governing equation, with the term the clicked block controls highlighted and explained in plain words; then how the run was solved (mesh, nodes, the sparsity pattern of K, the solve time).

```
js/pixels.js     pixel art: block icons (SVG data URIs) and Tri, the mascot
js/blocks.js     pixel renderer, themes, block definitions, toolbox, block explanations
js/generator.js  blocks → checks with friendly messages → FEAScript code
js/missions.js   missions and their starting workspaces
js/results.js    pixel heat maps, bar graphs, flow tracers, the animated front, "How it's solved"
js/app.js        workspace, running, missions, The math tab, Tri, save/open, theme
```

Blockly 12 (Apache 2.0) and FEAScript load from CDNs. FEAScript is pinned to a release (`FEASCRIPT_VERSION` in `js/app.js` and `critical-mesh/js/config.js`); bump it on purpose and replay the missions and shifts. Progress is kept in `localStorage` (`femBlocks.v1`). Both apps also work from `file://`.

## Name

The full name is **Tri's Lab by FEAScript**: please use it in titles, headings and posts (search engines ignore the apostrophe, so "Tri's Lab" alone gets mixed up with Tri-Lab, TriLab and Tris Lab). "Tri's Lab" alone is fine once the full name has been used.

## Contributing

Issues and pull requests are welcome: new missions, Field Notes, translations, bug reports. Please sign off your commits (`git commit -s`, [DCO](https://developercertificate.org)). Questions: [Discord](https://discord.gg/3DVjNcuW4f) or info@feascript.com.

## Licensing

Tri's Lab is code, writing and art, and each has its own terms:

| What | Licence |
|---|---|
| Code: everything not listed in the rows below | [MIT](LICENSE) |
| Writing and art: the story, dialogue and cast (`critical-mesh/js/story.js`), the Field Notes (`critical-mesh/js/codex.js`), the mission texts (`blocks/js/missions.js`), the pixel art (`critical-mesh/js/art.js`, `blocks/js/pixels.js`), the screenshots (`assets/*.png`) and the READMEs | [CC BY 4.0](LICENSE-CONTENT) |
| Tri (the character and its design, wherever it appears), the FEAScript logo, and the names "FEAScript" and "Tri's Lab" | Not licensed, all rights reserved |

In the files that mix code and writing or art, the code is MIT and the writing and art are CC BY 4.0; each of those files says so in its header. Credit CC BY material as: *"Tri's Lab by FEAScript (lab.feascript.com), CC BY 4.0"*, and note any changes you made.

**Tri and the FEAScript marks.** You may use Tri, the logos and the names, unchanged, when you refer to FEAScript or Tri's Lab: in a lesson, a talk, a blog post, or a fork that says where it comes from. For anything else (merchandise, a product or service, another project's mascot), please ask first at info@feascript.com. A fork you redistribute should replace Tri and the logos, or say clearly that it is not the official Tri's Lab.

Third-party software that Tri's Lab by FEAScript loads at runtime is listed in [NOTICE](NOTICE).
