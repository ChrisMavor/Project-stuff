# Project-stuff
Work in progress
##########################
# PART 1: Code
##########################

##########################
# Transposing a matrix 
##########################
def MatrixTranspose(matrix):
  B = [[0 for col in range(len(matrix))] for row in range(len(matrix[0]))] 
  for i in range(len(matrix)):
    for j in range(len(matrix[0])):
      B[j][i]=matrix[i][j]
  return B 

##########################
# Transposing a matrix 
##########################

def vecScalar(vec,scalar):
  row = [ ]
  for i in range(len(vec)):
      row.append(scalar*vec[i])
  return row

##########################
# Dot Product 
########################## 
def dot(vector01,vector02):
  """
  Inputs:
    vector01: vector in format of a list.
    vector02: vector in format of a list.
  Output:
    dot:
  This function 'dot' takes inputs in the format of lists, or vectors, and performs the dot product of the vectors. Dot product refers to the itemized multiplication of corresponding elements in each vector and sums the product of the itemized multiplication. 
  If there is a mistake in the formating, an error will result specifying the inputs to change in format type so that the function can opperate properly. 
  If proper inputs are given, the end result will return a integer called 'row'.
  """
  if type(vector01)==list and type(vector02)==list:
    if len(vector01)!=len(vector02):
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0]) == type(vector02[0]):
      dot=0 
      for i in range(len(vector01)):
        dot+=vector01[i]*vector02[i]
      return 'vector01 * vector02 =' , dot
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."

##########################
# PART 1: Question 1
##########################
def vandermondeProject(x,y):
  n=4
  m=len(x)
  if type(datax)== list and type(datay)==list:
    A=[]
    if type(datax[0])==list:
      return 'bad input value Change into row vector'
    else:
      for j in range(n):
        row=[]
        for i in range(m):
          row.append(datax[i]**j)
        A.append(row)
      A = MatrixTranspose(A)
      return A


datay=[1.102,1.099, 1.017, 1.111, 1.117, 1.152, 1.265, 1.380, 1.575, 1.857]
datax=[.55, .60, .65,.70,.75,.80,.85,.90,.95,1.00]
A = vandermondeProject(datax,datay)
print(A)
#print(vandermondeProject(datax,datay))

##########################
# PART 1: Question 2
##########################


def QRFactorization(A):
  QR=[]
  Q=[]
  V=MatrixTranspose(A)
  print(V)
 
  for i in range(len(V)): 
      rows=[]
      if i == 0:
        rows.append(V[i])
      elif i == 1:
        dot1= dot(V[i],V[i-1])
        print(dot1)
        proj2 = vecScalar(V[i],proj1)
        rows.append(V[i]-proj2)
      elif i == 2:
        proj= (dot(V[i-2],V[i])/dot(V[i-1],V[i-1]))
        proj1 = dot(V[i-1],V[i])*(dot(V[i-1],V[i-1]))**(-1)
        proj2 = vecScalar(V[i],proj1)
        proj3 = vecScalar(V[i],proj)
        rows.append(V[i]-proj2)
      print(rows) 

print(QRFactorization(A))
