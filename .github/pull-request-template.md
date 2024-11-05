/**
 * @import {Root as HastRoot} from 'hast'
 * @import {Root as MdastRoot} from 'mdast'
 * @import {Plugin} from 'unified'
 */

/**
 * @typedef Options
 *   Configuration (optional).
 * @property {boolean | null | undefined} [someField]
 *   Some option (optional).
 */

// To type options:
/** @type {Plugin<[(Options | null | undefined)?]>} */
export function myPluginAcceptingOptions(options) {
  const settings = options || {}
  // `settings` is now `Options`.
}

// To type a plugin that works on a certain tree, without options:
/** @type {Plugin<[], MdastRoot>} */
export function myRemarkPlugin() {
  return function (tree, file) {
    // `tree` is `MdastRoot`.
  }
}

// To type a plugin that transforms one tree into another:
/** @type {Plugin<[], MdastRoot, HastRoot>} */
export function remarkRehype() {
  return function (tree) {
    // `tree` is `MdastRoot`.
    // Result must be `HastRoot`.
  }
}

// To type a plugin that defines a parser:
/** @type {Plugin<[], string, MdastRoot>} */
export function remarkParse(options) {}

// To type a plugin that defines a compiler:
/** @type {Plugin<[], HastRoot, string>} */
export function rehypeStringify(options) {}type Transformer<
  Input extends Node = Node,
  Output extends Node = Input
> = (
  tree: Input,
  file: VFile,
  next: TransformCallback<Output>
) =>
  | Promise<Output | undefined>
  | Output
  | Error
  | undefinedinterface Settings {}declare module 'unified' {
  interface Settings {
    bullet: '*' | '+' | '-'
    // …
  }
}

export {} // You may not need this, but it makes sure the file is a module.[**@unifiedjs**](https://github.com/unifiedjs)https://github.com/unifiedjs<!--
  Please check the needed checkboxes ([ ] -> [x]). Leave the
  comments as they are, they won’t show on GitHub.
  We are excited about pull requests, but please try to limit the scope, provide
  a general description of the changes, and remember, it’s up to you to convince
  us to land it.
-->

### Initial checklist

* [ ] I read the support docs <!-- https://github.com/unifiedjs/.github/blob/main/support.md -->
* [ ] I read the contributing guide <!-- https://github.com/unifiedjs/.github/blob/main/contributing.md -->
* [ ] I agree to follow the code of conduct <!-- https://github.com/unifiedjs/.github/blob/main/code-of-conduct.md -->
* [ ] I searched issues and couldn’t find anything (or linked relevant results below) <!-- https://github.com/search?q=user%3Aunifiedjs&type=Issues -->
* [ ] If applicable, I’ve added docs and tests

### Description of changes

TODO

<!--do not edit: pr-->
