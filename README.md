# diagramas
#Funcion para diagrama de barras
species = ('Arnubi', 'compañero 2', 'compañero 3')
sex_counts = {
    'Male': np.array([55, 24, 61]),
    'Female': np.array([55, 34, 78]),
}
width = 0.6  # the width of the bars: can also be len(x) sequence


fig, ax = plt.subplots()
bottom = np.zeros(3)

for sex, sex_count in sex_counts.items():
    p = ax.bar(species, sex_count, width, label=sex, bottom=bottom)
    bottom += sex_count

    ax.bar_label(p, label_type='center')

ax.set_title('Number of penguins by sex')
ax.legend()

plt.show()
