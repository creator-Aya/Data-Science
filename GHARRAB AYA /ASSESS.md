
{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyNg8JsgKC1W6B5WkCQmTKwP",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/creator-Aya/Algo-Python/blob/main/CAC_2_GHARRAB_AYA_ASSESS_mdipynb.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "8tqOlwL4cxoB",
        "outputId": "4f42a9ca-89a3-444d-f598-b3b099253daa"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Collecting ucimlrepo\n",
            "  Downloading ucimlrepo-0.0.7-py3-none-any.whl.metadata (5.5 kB)\n",
            "Requirement already satisfied: pandas>=1.0.0 in /usr/local/lib/python3.12/dist-packages (from ucimlrepo) (2.2.2)\n",
            "Requirement already satisfied: certifi>=2020.12.5 in /usr/local/lib/python3.12/dist-packages (from ucimlrepo) (2025.10.5)\n",
            "Requirement already satisfied: numpy>=1.26.0 in /usr/local/lib/python3.12/dist-packages (from pandas>=1.0.0->ucimlrepo) (2.0.2)\n",
            "Requirement already satisfied: python-dateutil>=2.8.2 in /usr/local/lib/python3.12/dist-packages (from pandas>=1.0.0->ucimlrepo) (2.9.0.post0)\n",
            "Requirement already satisfied: pytz>=2020.1 in /usr/local/lib/python3.12/dist-packages (from pandas>=1.0.0->ucimlrepo) (2025.2)\n",
            "Requirement already satisfied: tzdata>=2022.7 in /usr/local/lib/python3.12/dist-packages (from pandas>=1.0.0->ucimlrepo) (2025.2)\n",
            "Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.12/dist-packages (from python-dateutil>=2.8.2->pandas>=1.0.0->ucimlrepo) (1.17.0)\n",
            "Downloading ucimlrepo-0.0.7-py3-none-any.whl (8.0 kB)\n",
            "Installing collected packages: ucimlrepo\n",
            "Successfully installed ucimlrepo-0.0.7\n"
          ]
        }
      ],
      "source": [
        "pip install ucimlrepo"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "from ucimlrepo import fetch_ucirepo\n",
        "\n",
        "# fetch dataset\n",
        "credit_approval = fetch_ucirepo(id=27)\n",
        "\n",
        "# data (as pandas dataframes)\n",
        "X = credit_approval.data.features\n",
        "y = credit_approval.data.targets\n",
        "\n",
        "# metadata\n",
        "print(credit_approval.metadata)\n",
        "\n",
        "# variable information\n",
        "print(credit_approval.variables)\n"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "s7WNko5dc7xv",
        "outputId": "2b4e6248-d0aa-456e-ae04-f9672557d5fc"
      },
      "execution_count": 2,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "{'uci_id': 27, 'name': 'Credit Approval', 'repository_url': 'https://archive.ics.uci.edu/dataset/27/credit+approval', 'data_url': 'https://archive.ics.uci.edu/static/public/27/data.csv', 'abstract': 'This data concerns credit card applications; good mix of attributes', 'area': 'Business', 'tasks': ['Classification'], 'characteristics': ['Multivariate'], 'num_instances': 690, 'num_features': 15, 'feature_types': ['Categorical', 'Integer', 'Real'], 'demographics': [], 'target_col': ['A16'], 'index_col': None, 'has_missing_values': 'yes', 'missing_values_symbol': 'NaN', 'year_of_dataset_creation': 1987, 'last_updated': 'Wed Aug 23 2023', 'dataset_doi': '10.24432/C5FS30', 'creators': ['J. R. Quinlan'], 'intro_paper': None, 'additional_info': {'summary': 'This file concerns credit card applications.  All attribute names and values have been changed to meaningless symbols to protect confidentiality of the data.\\r\\n  \\r\\nThis dataset is interesting because there is a good mix of attributes -- continuous, nominal with small numbers of values, and nominal with larger numbers of values.  There are also a few missing values.', 'purpose': None, 'funded_by': None, 'instances_represent': None, 'recommended_data_splits': None, 'sensitive_data': None, 'preprocessing_description': None, 'variable_info': 'A1:\\tb, a.\\r\\nA2:\\tcontinuous.\\r\\nA3:\\tcontinuous.\\r\\nA4:\\tu, y, l, t.\\r\\nA5:\\tg, p, gg.\\r\\nA6:\\tc, d, cc, i, j, k, m, r, q, w, x, e, aa, ff.\\r\\nA7:\\tv, h, bb, j, n, z, dd, ff, o.\\r\\nA8:\\tcontinuous.\\r\\nA9:\\tt, f.\\r\\nA10:\\tt, f.\\r\\nA11:\\tcontinuous.\\r\\nA12:\\tt, f.\\r\\nA13:\\tg, p, s.\\r\\nA14:\\tcontinuous.\\r\\nA15:\\tcontinuous.\\r\\nA16: +,-         (class attribute)', 'citation': None}}\n",
            "   name     role         type demographic description units missing_values\n",
            "0   A16   Target  Categorical        None        None  None             no\n",
            "1   A15  Feature   Continuous        None        None  None             no\n",
            "2   A14  Feature   Continuous        None        None  None            yes\n",
            "3   A13  Feature  Categorical        None        None  None             no\n",
            "4   A12  Feature  Categorical        None        None  None             no\n",
            "5   A11  Feature   Continuous        None        None  None             no\n",
            "6   A10  Feature  Categorical        None        None  None             no\n",
            "7    A9  Feature  Categorical        None        None  None             no\n",
            "8    A8  Feature   Continuous        None        None  None             no\n",
            "9    A7  Feature  Categorical        None        None  None            yes\n",
            "10   A6  Feature  Categorical        None        None  None            yes\n",
            "11   A5  Feature  Categorical        None        None  None            yes\n",
            "12   A4  Feature  Categorical        None        None  None            yes\n",
            "13   A3  Feature   Continuous        None        None  None             no\n",
            "14   A2  Feature   Continuous        None        None  None            yes\n",
            "15   A1  Feature  Categorical        None        None  None            yes\n"
          ]
        }
      ]
    }
  ]
}
