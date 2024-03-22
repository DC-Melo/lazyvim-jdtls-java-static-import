# lazyvim-jdtls-java-static-import
lazyvim config java static import

1. Add the configration favorite static members. Then java import static will work.
```bash
nvim $HOME/.local/share/nvim/lazy/nvim-jdtls/lua/jdtls/setup.lua
```

Add follow lines in to 
```lua
config.settings = vim.tbl_deep_extend("keep", config.settings or {}, {
  -- the `java` property is used in other places to detect the client as the jdtls client
  -- don't remove it without updating those places
  java = {
    jatureHelp = { enabled = true },
    contentProvider = { preferred = "fernflower" },
    completion = {
      favoriteStaticMembers = {
        "java.util.Objects.requireNonNull",
        "java.util.Objects.requireNonNullElse",
        "org.assertj.core.api.AssertionsForClassTypes.*",
        "org.hamcrest.CoreMatchers.*",
        "org.hamcrest.MatcherAssert.*",
        "org.hamcrest.Matchers.*",
        "org.junit.*",
        "org.junit.Assert.*",
        "org.junit.Assume.*",
        "org.junit.jupiter.api.Assertions.*",
        "org.junit.matchers.JUnitMatchers.*",
        "org.mockito.Mockito.*",
        "org.springframework.test.web.servlet.result.MockMvcResultMatchers.*",
      },
      filteredTypes = {
        "com.sun.*",
        "io.micrometer.shaded.*",
        "java.awt.*",
        "jdk.*",
        "sun.*",
      },
    },
  })
```


