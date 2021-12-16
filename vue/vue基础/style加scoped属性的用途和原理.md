用途：防止全局同名CSS污染
原理：在标签加上v-data-something属性，再在选择器时加上对应[v-data-something]，
即CSS带属性选择器，以此完成类似作用域的选择方式