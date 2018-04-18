# group by 
group by feature and apply aggregate function
pclass = titanic.groupby('Pclass')

# methods of group
print group.mean()
print group.median()
print group.count()
print group.max()
print group.size()
group.unstack()

group by criteria has empty cells above it
group by order matters
.reset_index(): will reset index to non hierachical

class_counts.plot(kind='bar', color='g', width=0.85)