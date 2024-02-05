# Streamlit-Project

import streamlit as st
#title
st.title("Copper(II)CarboxylatePaddlewheel Complexes")

#header
st.header("Hirshfield Surface Analysis")

#subheader
st.subheader(" - A visual representation of interatomic and intermolecular contacts within and between molecules")

st.write("Graphs/Plots are generated using the below equation:")

st.latex(r''' dnorm= di-RIvdw/RIvdw ⁄ de-REvdw/REvdw''')

st.write("where di and de are distances from the hirshfield surface to the nearest nucleus inside and outside the surface. /n RIvdw and REvdw are the van der Waals radii of the appropriate atoms.")

st.subheader("What exactly is the Hirshfield Surface?")


st.write("The Hirschfeld surface is defined as the area around a molecule in crystal space which separates two regions; namely that of the inner reference molecule and the outer neighboring molecules. The separation of that space by the Hirshfeld surfaces allows for the accurate analysis of intermolecular interactions of fingerprints in a crystalline medium. This type of analysis can be used to visualize and quantify non-covalent interactions that stabilize the crystal packing.")

#Data visualisation
#Complex 1
import pandas as pd
#assign data as list
st.text('Complex 1')
interatomic_contacts= ['Cu-Cu1', 'Cu-O1', 'C-O1', 'O-H1', 'C-H1', 'H-H1']
percentage_of_interatomic_contacts = [0,6,0.2,9.4,26.7,57.7]

interatomic_contact_percentage = {'interatomic_contacts':interatomic_contacts,'percentages':percentage_of_interatomic_contacts}

df= pd.DataFrame(interatomic_contact_percentage)

import pandas as pd
import matplotlib
matplotlib.use('TkAgg')
import matplotlib.pyplot as plt
import seaborn as sns

data = {'percentage_of_interatomic_contacts':[0,6,0.2,9.4,26.7,57.7]}
from tabulate import tabulate

data = [[0.0], [6.0], [0.2], [9.4], [26.7], [57.7]]
col_names = ["Interatomic_contacts", 'percentage_of_interatomic_contacts']
print(tabulate(data, headers = col_names, tablefmt="grid"))


df=pd.DataFrame(data, index = ['Cu-Cu1', 'Cu-O1', 'C-O1', 'O-H1', 'C-H1', 'H-H1'])
st.table(df)

import pandas as pd
import matplotlib
matplotlib.use('TkAgg')
import matplotlib.pyplot as plt
import seaborn as sns
st.title("Area Graph of Complex")
data = {'interatomic_percentages':[0,6,0.2,9.4,26.7,57.7]}
df=pd.DataFrame(data, index = ['Cu-Cu1', 'Cu-O1', 'C-O1', 'O-H1', 'C-H1', 'H-H1'])
st.area_chart(df)
import numpy as np
import png
import pandas as pd
df.plot.pie(y='interatomic_percentages', figsize=(10,10), autopct='%1.1f%%', startangle=90)
plt.title(label= "Percentage Interatomic Contacts in Complex 1", fontdict = {"fontsize":25},pad=20)
plt.show()
