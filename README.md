{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Thompson Sampling\n",
    "<hr>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Bayesian Inference\n",
    "\n",
    "* Ad *i* gets rewards **y** from Bernoulli distribution <code>*p(**y**|θ<sub>i</sub>) ~ ß(θ<sub>i</sub>)*</code>\n",
    "\n",
    "* *θ<sub>i</sub>* is unknown but we set its uncertainty by assuming it has a uniform distribution <code>*p(θ<sub>i</sub>)* ~ *u*([0, 1])</code>, which is the prior distribution.\n",
    "\n",
    "* **Bayes Rule:** We approach *θ<sub>i</sub>* by the posterior distribution\n",
    "<img src=\"image.png\" width=\"1000px\">\n",
    "\n",
    "* We get <code>*p(θ<sub>i</sub>|**y**) ~ ß(number of successes + 1, number of failures + 1)*</code>\n",
    "\n",
    "* At each round *n* we take a random draw *θ<sub>i</sub>(n)* from this posterior distribution *`p(θ<sub>i</sub>|**y**)`*, for each ad *i*.\n",
    "\n",
    "* At each round *n* we select the ad *i* that has the highest *θ<sub>i</sub>(n)*."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<hr>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Thompson Sampling Algorithm\n",
    "\n",
    "**Step 1:** At each round *n*, we consider two numbers for each ad *i*:\n",
    "* *N<sup>1</sup><sub>i</sub>(n)* - the number of times the ad *i* got reward *1* up to round *n*.\n",
    "* *N<sup>0</sup><sub>i</sub>(n)* - the number of times the ad *i* got reward *0* up to round *n*.\n",
    "\n",
    "**Step 2:** For each ad *i*, we take a random draw from the distribution below:\n",
    "\n",
    "&emsp;&emsp;&emsp;&emsp;&emsp;<code>θ<sub>i</sub>(n) = ß(N<sup>1</sup><sub>i</sub>(n) + 1, N<sup>0</sup><sub>i</sub>(n) + 1)</code>\n",
    "\n",
    "**Step 3:** We select the ad that has the highest *θ<sub>i</sub>(n)*."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<hr>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## UCB Algorithm v/s Thompson Sampling Algorithm\n",
    "\n",
    "<table>\n",
    "    <tr>\n",
    "        <th>Upper Confidence Bound</th>\n",
    "        <th>Thompson Sampling</th>\n",
    "    </tr>\n",
    "    <tr>\n",
    "        <td><img src=\"image-1.png\" alt=\"UCB\" width=\"500px\"></td>\n",
    "        <td><img src=\"image-2.png\" alt=\"Thompson Sampling\" width=\"500px\" height=\"250px\"></td>\n",
    "    </tr>\n",
    "    <tr>\n",
    "        <td>Deterministic</td>\n",
    "        <td>Probabilistic</td>\n",
    "    </tr>\n",
    "</table>"
   ]
  }
 ],
 "metadata": {
  "language_info": {
   "name": "python"
  },
  "orig_nbformat": 4
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
