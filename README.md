# query-request-using-openai-from-pdfs-uploaded
This code can be used to remove any special characters and number from any test messages from uploaded documents
!pip install langchain
!pip install unstructured
!pip install openai
!pip install chromadb
!pip install Cython
!pip install tiktoken
from langchain.document_loaders import UnstructuredPDFLoader
from langchain.indexes import VectorstoreIndexCreator
import os
os.environ["OPENAI_API_KEY"]='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'
from google.colab import drive
drive.mount('/content/gdrive',force_remount=True)
root_dir='/content/gdrive/MyDrive/'
pdf_folder_path=f'{root_dir}GPT/'
os.listdir(pdf_folder_path)
!pip install pdf2image
index=VectorstoreIndexCreator().from_loaders(loaders)
index
index.query('what is micro')
index.query_with_sources('Types')
index.query_with_sources('What do you want')
