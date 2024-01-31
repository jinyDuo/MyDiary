<h1>.eslintrc.json</h1>
{
  "parser": "@typescript-eslint/parser",
  "plugins": ["react", "@typescript-eslint", "prettier"],
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended"
  ],
  "rules": {
    "@typescript-eslint/explicit-module-boundary-types": "off",
    "import/order": ["error", {"newlines-between": "always"}],
    "no-unused-vars": "error"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
