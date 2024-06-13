# Welcome to Elixir cheat sheet!

**Create authentication in Phoenix project**
`mix phx.gen.auth Accounts User users --hashing-lib argon2`

**Add common dependencies**
`{:credo, "~> 1.7", only: [:dev, :test], runtime: false}`
`{:mix_unused, "~> 0.4.1", only: [:dev, :test], runtime: false}`
`{:sobelow, "~> 0.13", only: [:dev, :test], runtime: false}`

**After installation you need to add `:unused` as a compiler to the list of Mix compilers in `project` function**
`compilers: [:unused] ++ Mix.compilers()`

