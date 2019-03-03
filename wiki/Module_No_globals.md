---
title: Module:No globals
permalink: wiki/Module:No_globals/
layout: wiki
---

local mt = getmetatable(\_G) or {} function mt.\_\_index (t, k)

`   if k ~= 'arg' then`  
`       error('Tried to read nil global ' .. tostring(k), 2)`  
`   end`  
`   return nil`

end function mt.\_\_newindex(t, k, v)

`   if k ~= 'arg' then`  
`       error('Tried to write global ' .. tostring(k), 2)`  
`   end`  
`   rawset(t, k, v)`

end setmetatable(\_G, mt)
