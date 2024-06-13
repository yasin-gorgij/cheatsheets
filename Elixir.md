# Welcome to Elixir cheat sheet!

**Add language server directories to project .gitignore file***
`# Language server directories`
`/.elixir_ls/`
`/.elixir-tools/`

**Create authentication in Phoenix project**
`mix phx.gen.auth Accounts User users --hashing-lib argon2`

**Add common dependencies**
`{:credo, "~> 1.7", only: [:dev, :test], runtime: false}`
`{:mix_unused, "~> 0.4.1", only: [:dev, :test], runtime: false}`
`{:sobelow, "~> 0.13", only: [:dev, :test], runtime: false}`

**After installation you need to add `:unused` as a compiler to the list of Mix compilers in `project` function**
`compilers: [:unused] ++ Mix.compilers()`

**Then you just need to run `mix compile` or `mix compile --force` as usual and unused hints will be added to the end of the output.**

**Run `mix hex.audit` after adding a dependency or from time to time to check for retired hex package***

