# Pivot tables
pd.pivot_table(df,
			columns=['variable'],
			values='value',
			index=['subject_id'],
			aggfunc=select_item_or nan,
			fill_value=np.nan)

# logical flow of handling long pd df
# Making a long df
style_columns = ['affiliative','selfenhancing','aggressive','selfdefeating']
question_columns = column_change.values()
to_value_variable_columns = style_columns + question_columns + ['accuracy']

id_columns = ['subject_id','age','gender']

hsq_long = pd.melt(hsq, id_vars=id_columns, value_vars=to_value_variable_columns,
                   var_name='variable', value_name='value')
- RESET INDEX
hsq_long.sort_values('subject_id', inplace=True)
hsq_long.head()

hsq_long.reset_index(drop=True, inplace=True)
hsq_long.head()


# removing records based on condition
unresponded = hsq_long[hsq_long.value == -1]

incomplete_subs = unresponded.subject_id.value_counts()

hsq_long = hsq_long[~hsq_long.subject_id.isin(bad_subjects)]

